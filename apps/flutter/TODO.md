# Flutter Port - Remaining Work

This file tracks remaining work for the ComfyUI Flutter port.

## Phase 4: UI Components

### ComfyNode Widget
- [ ] Node header with title and category color
- [ ] Input slots with labels and connection dots
- [ ] Output slots with labels and connection dots
- [ ] Widget rendering for INT, FLOAT, STRING, COMBO inputs
- [ ] Collapsed state support
- [ ] Selection highlighting
- [ ] Muted/bypassed visual states

### ComfyEdge Widget
- [ ] Bezier curve rendering (default)
- [ ] Step edge type
- [ ] Smoothstep edge type
- [ ] Straight edge type
- [ ] Type-based coloring
- [ ] Animation support
- [ ] Selection highlighting

### Node Search Panel
- [ ] Fuzzy search with ranking (uses existing NodeRegistry.search())
- [ ] Category tree navigation
- [ ] Recent nodes section
- [ ] Keyboard navigation
- [ ] Double-click to add node
- [ ] Drag to add at position
- [ ] Display node descriptions

### Properties Panel
- [ ] Display selected node info
- [ ] Edit widget values
- [ ] Show input/output connections
- [ ] Node settings (muted, bypassed)

## Phase 5: State Management

### Riverpod Providers
- [ ] GraphNotifier for graph state
- [ ] NodeRegistryProvider for node definitions
- [ ] SelectionProvider for selected nodes/edges
- [ ] ExecutionProvider for execution state
- [ ] ConnectionProvider for WebSocket connection state
- [ ] Settings providers

## Phase 6: Backend Integration

### WebSocket Service
- [ ] WebSocket connection management
- [ ] Automatic reconnection
- [ ] Message parsing (execution progress, status, errors)
- [ ] Execution queue status tracking
- [ ] Image preview streaming
- [ ] Error handling and recovery

### ComfyAPI Service
- [ ] /object_info endpoint (node definitions)
- [ ] /prompt endpoint (queue execution)
- [ ] /queue endpoint (queue status)
- [ ] /history endpoint (execution history)
- [ ] /view endpoint (image viewing)
- [ ] /upload/image endpoint (image upload)

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

- [ ] Integration tests for graph operations
- [ ] Widget tests for UI components
- [ ] Mock WebSocket for testing
- [ ] Golden tests for node rendering
