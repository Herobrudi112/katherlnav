# Navigation Graph System

A dual-application system for creating and viewing indoor navigation graphs.

## Applications

### 1. Editor (`editor.html`)
**Full-featured graph editor** for creating and modifying navigation networks.

**Features:**
- Add/remove nodes (rooms) by clicking on canvas
- Connect/disconnect nodes with automatic or manual weights
- Drag nodes to reposition them
- **Manual weight editing** - Right-click edges to set custom weights
- Import from rooms.json or custom JSON
- Export graphs for use in the navigator
- Find shortest paths between rooms
- Multi-select nodes with Shift+Click

**Usage:**
1. Open `editor.html` in your browser
2. Click on canvas to add rooms
3. Shift+Click two nodes to select them, then click "Connect selected"
4. Right-click edges to edit weights manually
5. Use "Export for Navigator" to save your graph
6. Load existing graphs with "Import" or "Load rooms.json"

### 2. Navigator (`navigator.html`)
**View-only graph viewer** for exploring exported navigation graphs.

**Features:**
- Load exported graphs via drag & drop or file browser
- Pan and zoom navigation
- Click nodes to see detailed information
- Find shortest paths between rooms
- View graph statistics (node count, edge count, total weight)
- No editing capabilities - preserves graph integrity

**Usage:**
1. Open `navigator.html` in your browser
2. Drag & drop a JSON graph file or click to browse
3. Navigate with mouse drag (pan) and scroll wheel (zoom)
4. Click nodes to see details
5. Enter start/end room names to find shortest paths

## File Format

Both applications use the same JSON format:

```json
{
  "nodes": [
    {
      "id": 1,
      "name": "Room A",
      "longName": "Full Room Name",
      "x": 100,
      "y": 200,
      "building": "Building Name"
    }
  ],
  "edges": [
    {
      "from": 1,
      "to": 2,
      "weight": 50
    }
  ]
}
```

## Manual Weight System

The editor supports **manual weight assignment**:

1. **Automatic weights**: When connecting nodes, weights default to the Euclidean distance
2. **Manual weights**: Right-click any edge to open the weight editor
3. **Weight editing**: Set custom values or reset to automatic distance
4. **Weight display**: All weights are shown on the graph

## Workflow

1. **Design**: Use the editor to create your navigation graph
2. **Test**: Find paths and verify connectivity
3. **Export**: Use "Export for Navigator" to save your graph
4. **Share**: Distribute the JSON file to users
5. **Navigate**: Users open the navigator to explore your graph

## Technical Details

- **Canvas-based rendering** for smooth performance
- **Dijkstra's algorithm** for shortest path finding
- **Responsive design** that works on various screen sizes
- **Touch-friendly** interactions for mobile devices
- **High DPI support** for retina displays

## Browser Compatibility

Works in all modern browsers that support:
- HTML5 Canvas
- ES6+ JavaScript
- CSS Grid and Flexbox
- File API for drag & drop

## Getting Started

1. Open `editor.html` to start building your navigation graph
2. Add rooms by clicking on the canvas
3. Connect rooms by selecting two nodes and clicking "Connect selected"
4. Customize weights by right-clicking edges
5. Export your graph for use in the navigator
6. Test the navigator by opening `navigator.html` and loading your exported graph

