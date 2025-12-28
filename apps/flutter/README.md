# ComfyUI Flutter Port

Flutter implementation of the ComfyUI node graph editor, designed to work with the ComfyUI backend.

## Architecture

The Flutter port follows a clean architecture pattern:

```
flutter/
├── core/
│   ├── nodes/          # Node definitions and registry
│   │   ├── node_definition.dart    # NodeDefinition, WidgetDefinition
│   │   ├── node_registry.dart      # NodeRegistry with search
│   │   └── slot_types.dart         # SlotType enum and SlotDefinition
│   ├── graph/          # Graph container and algorithms
│   │   ├── comfy_graph.dart        # ComfyGraph, ComfyNode, ComfyEdge
│   │   ├── graph_validator.dart    # Validation logic
│   │   └── topological_sort.dart   # Execution order
│   └── serialization/  # JSON format handling
│       ├── workflow_json.dart      # ComfyUI workflow format
│       └── api_format.dart         # API prompt format
└── test/               # Unit tests
```

## Key Features Implemented

### Node System
- **SlotType**: 24 slot types with colors matching ComfyUI TypeScript frontend
- **SlotDefinition**: Input/output slot definitions with type checking
- **NodeDefinition**: Complete node definition parsing from API
- **NodeRegistry**: Node registration, search, and category tree

### Graph Core
- **ComfyGraph**: Graph container with node/edge management
- **ComfyNode**: Node instances with widget values and properties
- **ComfyEdge**: Type-safe connections between nodes
- **ComfyGroup**: Node grouping for organization

### Algorithms
- **Topological Sort**: Kahn's algorithm for execution order
- **Graph Validation**: Type checking, cycle detection, required inputs
- **Connection Validation**: Type compatibility checking

### Serialization
- **Workflow JSON**: Import/export ComfyUI workflow format
- **API Format**: Generate prompts for backend execution

## Usage

```dart
import 'package:comfyui_flutter/core/graph/comfy_graph.dart';
import 'package:comfyui_flutter/core/nodes/node_registry.dart';

// Load node definitions from ComfyUI API
final registry = NodeRegistry();
await registry.loadFromApiUrl('http://localhost:8188/object_info');

// Create a graph
final graph = ComfyGraph(registry: registry);

// Add nodes
final loader = graph.addNodeByType('CheckpointLoaderSimple', Offset(0, 0));
final sampler = graph.addNodeByType('KSampler', Offset(300, 0));

// Connect nodes
graph.connect(loader!.id, 0, sampler!.id, 0); // MODEL output to model input

// Validate
final validator = GraphValidator(registry);
final result = validator.validate(graph);
if (!result.isValid) {
  print('Validation errors: ${result.errors}');
}

// Serialize
final json = WorkflowSerializer.toJsonString(graph, pretty: true);
```

## Dependencies

- Flutter 3.10+
- Dart SDK 3.0+
- xyflow_flutter (for canvas rendering)

## Running Tests

From the xyflow example directory:
```bash
flutter test test/comfyui/
```

## Roadmap

See [IMPLEMENTATION_PLAN.md](./IMPLEMENTATION_PLAN.md) for detailed implementation status.

### Phase 1: Core Data Models (Complete)
- [x] SlotType enum and colors
- [x] SlotDefinition class
- [x] NodeDefinition class
- [x] WidgetDefinition class
- [x] NodeRegistry with search

### Phase 2: Graph Core (Complete)
- [x] ComfyGraph container
- [x] ComfyNode instances
- [x] ComfyEdge connections
- [x] Topological sort
- [x] Graph validation

### Phase 3: Serialization (Complete)
- [x] Workflow JSON format
- [x] API prompt format
- [x] Execution result parsing

### Phase 4: UI Components (In Progress)
- [ ] ComfyNode widget
- [ ] ComfyEdge widget
- [ ] Node search panel
- [ ] Properties panel

### Phase 5: Backend Integration (Pending)
- [ ] WebSocket client
- [ ] Execution queue
- [ ] Progress tracking
- [ ] Image preview

## License

Same license as parent ComfyUI_frontend repository.
