# Flutter Port - Remaining Work

This file tracks remaining work for the ComfyUI Flutter port.

## Phase 4: UI Components

### ComfyNode Widget
- [x] Node header with title and category color
- [x] Input slots with labels and connection dots
- [x] Output slots with labels and connection dots
- [x] Widget rendering for INT, FLOAT, STRING, COMBO inputs
- [x] Collapsed state support
- [x] Selection highlighting
- [x] Muted/bypassed visual states

### ComfyEdge Widget
- [x] Bezier curve rendering (default)
- [x] Step edge type
- [x] Smoothstep edge type
- [x] Straight edge type
- [x] Type-based coloring
- [x] Animation support
- [x] Selection highlighting

### Node Search Panel
- [x] Fuzzy search with ranking (uses existing NodeRegistry.search())
- [x] Category tree navigation
- [x] Recent nodes section
- [x] Keyboard navigation
- [x] Double-click to add node
- [ ] Drag to add at position
- [x] Display node descriptions

### Properties Panel
- [x] Display selected node info
- [x] Edit widget values
- [x] Show input/output connections
- [x] Node settings (muted, bypassed)

## Phase 5: State Management

### Riverpod Providers
- [x] GraphNotifier for graph state
- [x] NodeRegistryProvider for node definitions
- [x] SelectionProvider for selected nodes/edges
- [x] ExecutionProvider for execution state
- [x] ConnectionProvider for WebSocket connection state
- [ ] Settings providers

## Phase 6: Backend Integration

### WebSocket Service
- [x] WebSocket connection management
- [x] Automatic reconnection
- [x] Message parsing (execution progress, status, errors)
- [x] Execution queue status tracking
- [x] Image preview streaming
- [x] Error handling and recovery

### ComfyAPI Service
- [x] /object_info endpoint (node definitions)
- [x] /prompt endpoint (queue execution)
- [x] /queue endpoint (queue status)
- [x] /history endpoint (execution history)
- [x] /view endpoint (image viewing)
- [x] /upload/image endpoint (image upload)

## Phase 7: Advanced Features

### Subgraph Support
- [ ] Subgraph creation
- [ ] Subgraph editing
- [ ] Subgraph node type
- [ ] Input/output mapping

### Reroute Nodes
- [ ] Reroute node type
- [ ] Visual rendering
- [ ] Connection chaining

### Workflow Management
- [ ] Save/load workflow
- [ ] Export to API format
- [ ] Import from JSON
- [ ] Undo/redo support

## Testing

- [x] Unit tests for core functionality (77 tests passing)
- [ ] Integration tests for graph operations
- [ ] Widget tests for UI components
- [ ] Mock WebSocket for testing
- [ ] Golden tests for node rendering
