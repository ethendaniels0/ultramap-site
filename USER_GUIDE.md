# ultramap - User Guide

## Table of Contents

1. [Introduction](#introduction)
2. [Getting Started](#getting-started)
3. [Core Concepts](#core-concepts)
4. [Working with Content](#working-with-content)
5. [Connections and Relationships](#connections-and-relationships)
6. [AI-Powered Features](#ai-powered-features)
7. [AI Assistant Integration](#ai-assistant-integration)
8. [Organization Tools](#organization-tools)
9. [Keyboard Shortcuts](#keyboard-shortcuts)
10. [Advanced Features](#advanced-features)
11. [Tips and Best Practices](#tips-and-best-practices)

---

## Introduction

**ultramap** is a premium desktop application that combines visual whiteboarding with AI-powered knowledge management. It provides an infinite canvas where you can capture ideas, organize information, and discover connections between your thoughts using semantic search and automatic relationship detection.

### Key Features

- **AI Assistant Integration**: Collaborate and brainstorm with the AI Assistants you already have.
- **Infinite Canvas**: Pan and zoom freely across an unlimited workspace
- **Multiple Content Types**: Sticky notes, shapes, text, frames, website cards, and embedded videos
- **Multiple Boards**: Create and manage separate whiteboards for different projects

### Platform Support

ultramap is available for:
- **macOS**: DMG and ZIP installers
- **Windows**: NSIS installer and portable executable
- **Linux**: AppImage and DEB packages

---

## Getting Started

### First Launch

When you first open ultramap, you'll see an empty canvas with a toolbar on the left side. The canvas uses a dot grid background to help with spatial organization.

### Navigation

- **Pan**: Click and drag with the **middle mouse button** or use the **scroll wheel** while holding **Shift**
- **Zoom**: Use the **scroll wheel** or the zoom controls in the bottom-right corner
- **Zoom Shortcuts**:
  - `Cmd/Ctrl + 0`: Reset zoom and fit view
  - `Cmd/Ctrl + +`: Zoom in
  - `Cmd/Ctrl + -`: Zoom out

### Creating Your First Note

1. Press **S** or click the Sticky Note tool in the toolbar
2. Click anywhere on the canvas to place a sticky note
3. Type your content directly into the note
4. Click outside the note or press **Escape** to finish editing

---

## Core Concepts

### Nodes

Nodes are the fundamental building blocks in ultramap. Each node has:
- **Type**: Determines appearance and behavior (sticky note, shape, text, etc.)
- **Content**: The text or data stored in the node
- **Position**: X and Y coordinates on the canvas
- **Size**: Width and height in pixels
- **Style**: Visual properties like colors, fonts, and borders
- **Metadata**: Additional information like z-index, parent relationships, etc.

### Edges

Edges are connections between nodes. There are two types:

1. **User-Created Edges**: Visible connections you draw manually
2. **System-Generated Edges**: Automatic relationships discovered by the AI:
   - `similar_to`: Semantically related content (based on embeddings)
   - `near`: Spatially close nodes on the canvas
   - `parent_of`: Frame containment relationships
   - `grouped_with`: Nodes co-located in the same frame

### Boards

A board is a self-contained workspace with its own nodes, edges, and data. You can:
- Create multiple boards for different projects
- Save boards to specific locations
- Open existing boards
- Access recently opened boards via the File menu

---

## Working with Content

### Node Types

#### Sticky Notes (S)

The classic sticky note for quick ideas and reminders.

- **Create**: Press `S` and click on the canvas
- **Default Size**: 200x150 pixels
- **Customization**: Background color, text color, font size
- **Use Cases**: Brainstorming, quick notes, task tracking

#### Text Nodes (T)

Plain text without the sticky note styling, ideal for labels and annotations.

- **Create**: Press `T` and click on the canvas
- **Default Size**: 200x100 pixels
- **Customization**: Font size, font family, text color, alignment
- **Use Cases**: Titles, labels, annotations, headers

#### Shapes

**Rectangle (R)** and **Circle/Ellipse (E)** shapes for diagrams and visual organization.

- **Create**: Press `R` (rectangle) or `E` (ellipse) and click on the canvas
- **Default Size**: 200x200 pixels
- **Customization**: Fill color, border color, border width, border style
- **Use Cases**: Flowcharts, diagrams, visual containers, highlighting areas

#### Frames (F)

Container nodes that visually group and organize related content.

- **Create**: Select multiple nodes, then press `Cmd/Ctrl + G`
- **Behavior**: Child nodes move with the frame and have relative positions
- **Customization**: Background color, border color, title
- **Use Cases**: Grouping related ideas, organizing sections, creating hierarchies

#### Website Cards (W)

Rich preview cards that display website metadata.

- **Create**: Press `W` and enter a URL
- **Features**:
  - Automatic metadata fetching (title, description, favicon, preview image)
  - Clickable link to open in browser
  - Visual preview with OpenGraph data
- **Use Cases**: Research bookmarks, reference materials, inspiration boards

#### YouTube Cards (Y)

Embedded YouTube video players with metadata.

- **Create**: Press `Y` and enter a YouTube URL
- **Features**:
  - Inline video playback
  - Thumbnail, title, and channel information
  - Direct integration with YouTube API
- **Use Cases**: Tutorial collections, presentation materials, video research

### Editing Content

1. **Double-click** any node to enter edit mode
2. **Press Enter** when a single node is selected to start editing
3. Type your content (supports multi-line text)
4. Click outside or press **Escape** to finish

### Styling Nodes

When you select a node, a Node Toolbar appears above it with styling options:

- **Background Color**: Change the fill color
- **Text Color**: Adjust text appearance
- **Border Color**: Modify the outline color
- **Border Width**: Set border thickness (1-10 pixels)
- **Font Size**: Adjust text size (8-48 pixels)
- **Font Weight**: Normal or bold text

### Resizing and Rotating

- **Resize**: Drag the corner handles of a selected node
- **Maintain Aspect Ratio**: Hold **Shift** while dragging a corner
- **Rotate**: Drag the rotation handle above a selected node

### Copy, Paste, and Duplicate

- **Copy**: Select nodes and press `Cmd/Ctrl + C`
- **Paste**: Press `Cmd/Ctrl + V` (nodes appear at your last click position)
- **Duplicate**: Select nodes and press `Cmd/Ctrl + D` (offset by 50 pixels)
- **Paste URLs**: Copy a URL and paste it on the canvas to automatically create a website or YouTube card

### Deleting Nodes

- Select nodes and press **Delete** or **Backspace**
- Deleting a frame will unframe its children (they remain on the canvas)
- All connected edges are automatically deleted (CASCADE behavior)

---

## Connections and Relationships

### Creating Connectors

1. **Method 1**: Press `C` and draw connections appear when you hover over nodes
2. **Method 2**: Drag from a node's edge to connect to another node
3. Connectors snap to connection handles on each side of nodes

### Connection Handles

Each node has four connection handles:
- **Top**
- **Right**
- **Bottom**
- **Left**

The system automatically routes edges for clean, professional diagrams.

### Edge Styles

When you select an edge, an Edge Toolbar appears with options:

- **Path Type**:
  - `default`: Smooth bezier curves
  - `smoothstep`: Orthogonal routing with rounded corners
  - `step`: Sharp orthogonal routing
  - `straight`: Direct line
- **Color**: Edge color (default: black)
- **Width**: Line thickness (1-5 pixels)
- **Arrow Style**: Solid, dashed, or dotted
- **Label**: Text description on the edge
- **Markers**: Arrow heads at start and/or end

### Reconnecting Edges

- Drag an edge's end point to reconnect it to a different node
- The system preserves styling when reconnecting

### Smart Relationships

ultramap uses a knowledge graph to represent your whiteboard. This enables AI assistants to have a deep understanding of the content and how concepts relate to eachother. 

---

## AI Assistant Integration

ultramap's most powerful feature is the ability to connect AI assistants to help you brainstorm or gain insights. This is done through an open standard (model context protocol).

### Supported AI Assistants

- **Claude Desktop**: Anthropic's desktop application
- **Claude Code**: OpenAI's desktop application
- **VS Code**: With MCP extension support

### How It Works

ultramap includes an **MCP (Model Context Protocol) Server** that:

1. Starts automatically when ultramap and your assistant are running
2. Exposes tools that AI assistants can use
4. Enables natural language control of your whiteboard

### Setting Up AI Assistants

#### Quick Setup (Recommended)

1. Open **AI Assistants** settings:
   - Click the menu bar → **View** → **AI Assistants**
   - Or press `Cmd/Ctrl + ,` and navigate to AI Assistants
2. Select your AI assistant (e.g. Claude Desktop)
3. Click **"Connect [Assistant Name]"** to auto-configure
4. Restart your AI assistant to activate the connection

#### Manual Setup

If auto-configuration doesn't work:

1. Click **"Open Config File"** to open the AI assistant's configuration
2. Click **"Copy"** to copy the configuration snippet
3. Paste it into the appropriate location in the config file
4. Save and restart your AI assistant

### AI Assistant Capabilities

Your AI assistant has the ability to do anything you could do in the whiteboard, so you can focus on working with together.

#### Content Creation
- `create_sticky_note`: Create sticky notes with custom colors
- `create_text_node`: Create plain text nodes
- `create_rectangle`: Create rectangle shapes
- `create_ellipse`: Create circle/ellipse shapes
- `create_frame`: Create container frames
- `create_website_card`: Add website preview cards
- `create_youtube_card`: Add YouTube video cards

#### Content Management
- `get_node_details`: View detailed information about a node
- `update_node_content`: Change text content
- `update_node_style`: Modify visual styling
- `move_node`: Reposition nodes
- `resize_node`: Change dimensions
- `delete_node`: Remove nodes
- `duplicate_node`: Create copies

#### Search and Discovery
- `search_board`: Semantic search across all content
- `find_similar_notes`: Find content related to a specific node
- `get_board_overview`: Get a summary of the entire board
- `get_all_nodes`: List all nodes with filtering

#### Connections
- `create_connector`: Draw edges between nodes
- `delete_connector`: Remove edges
- `get_node_connections`: View all edges for a node

#### Organization
- `organize_notes_grid`: Auto-arrange nodes in a grid layout
- `filter_nodes_by_type`: Query by content type

#### Graph Analysis
- `get_neighbors`: Find directly connected nodes
- `explore_connected_nodes`: Traverse the graph (BFS)
- `find_path`: Find shortest path between nodes
- `find_weighted_path`: Find strongest conceptual path
- `get_system_relationships`: View auto-discovered relationships
- `get_clusters`: Detect communities of related nodes
- `get_connected_components`: Find isolated graph islands
- `get_graph_overview`: View graph statistics

### Example AI Assistant Commands

Once connected, you can give natural language commands to your AI assistant:

**Creating Content**:
- "Create a sticky note at position 100, 200 that says 'Meeting notes'"
- "Add 5 yellow sticky notes with ideas for the marketing campaign"
- "Create a frame titled 'Q1 Goals' at x=500, y=300 with width 800 and height 600"

**Organizing**:
- "Arrange all my sticky notes in a 4-column grid starting at position 0, 0"
- "Find all nodes about project management and organize them"
- "Group all the marketing-related notes into a frame"

**Searching**:
- "Search for notes about deadlines and show me the top 5 results"
- "Find content similar to node abc-123"
- "What's on my board? Give me an overview"

**Analysis**:
- "Show me all the connections for this node"
- "Find related clusters of ideas on my board"
- "What notes are semantically similar to my 'AI Strategy' note?"
- "Map the path between node A and node B"

### MCP Resources

Your AI assistant can also access:

- **Recent Changes**: View the last 50 operations (create/update/delete) with differential change tracking

This allows the AI to be aware of recent modifications and provide contextual assistance.

---

## Organization Tools

### Alignment Tools

When you select multiple nodes, an Alignment Toolbar appears at the top:

- **Align Left** (`Cmd/Ctrl + Shift + L`): Align to leftmost edge
- **Align Right** (`Cmd/Ctrl + Shift + R`): Align to rightmost edge
- **Align Top** (`Cmd/Ctrl + Shift + T`): Align to top edge
- **Align Bottom** (`Cmd/Ctrl + Shift + B`): Align to bottom edge
- **Distribute Horizontal** (`Cmd/Ctrl + Shift + H`): Space evenly horizontally (3+ nodes)
- **Distribute Vertical** (`Cmd/Ctrl + Shift + V`): Space evenly vertically (3+ nodes)

### Grouping with Frames

Frames are powerful organizational tools:

1. **Create a Frame**: Select 2+ nodes and press `Cmd/Ctrl + G`
2. **Frame Behavior**:
   - Selected nodes become children of the frame
   - Children use relative coordinates
   - Moving the frame moves all children
3. **Unframe**: Select a frame and press `Cmd/Ctrl + Shift + G`
   - Children are converted back to absolute positions
   - Children remain on the canvas after unframing

### Z-Order (Layering)

Control which nodes appear in front:

- **Bring to Front**: Right-click → "Bring to Front"
- **Send to Back**: Right-click → "Send to Back"
- **Frames**: Always render behind their children (z-index: -1)

### Selection

- **Single Selection**: Click a node
- **Multiple Selection**:
  - Hold **Shift** and click nodes
  - Drag a selection box (when Select tool is active)
- **Select All**: `Cmd/Ctrl + A`

---

## Keyboard Shortcuts

### Tools

| Shortcut | Tool |
|----------|------|
| `V` | Select tool |
| `S` | Sticky note |
| `R` | Rectangle |
| `E` | Circle/Ellipse |
| `T` | Text |
| `C` | Connector |
| `W` | Website card |
| `Y` | YouTube card |

### Navigation and View

| Shortcut | Action |
|----------|--------|
| `Cmd/Ctrl + 0` | Fit view / Reset zoom |
| `Cmd/Ctrl + +` | Zoom in |
| `Cmd/Ctrl + -` | Zoom out |
| `Cmd/Ctrl + F` | Open search panel |
| `Escape` | Cancel / Deselect / Close |

### Editing

| Shortcut | Action |
|----------|--------|
| `Enter` | Edit selected node |
| `Delete` / `Backspace` | Delete selected nodes/edges |
| `Cmd/Ctrl + Z` | Undo |
| `Cmd/Ctrl + Shift + Z` | Redo |
| `Cmd/Ctrl + Y` | Redo (Windows) |

### Clipboard

| Shortcut | Action |
|----------|--------|
| `Cmd/Ctrl + C` | Copy selected nodes |
| `Cmd/Ctrl + V` | Paste nodes (or create URL card from clipboard) |
| `Cmd/Ctrl + D` | Duplicate selected nodes |

### Organization

| Shortcut | Action |
|----------|--------|
| `Cmd/Ctrl + G` | Group selection into frame |
| `Cmd/Ctrl + Shift + G` | Ungroup/unframe |
| `Cmd/Ctrl + A` | Select all nodes |

### Alignment (with selection)

| Shortcut | Action |
|----------|--------|
| `Cmd/Ctrl + Shift + L` | Align left |
| `Cmd/Ctrl + Shift + R` | Align right |
| `Cmd/Ctrl + Shift + T` | Align top |
| `Cmd/Ctrl + Shift + B` | Align bottom |
| `Cmd/Ctrl + Shift + H` | Distribute horizontal (3+ nodes) |
| `Cmd/Ctrl + Shift + V` | Distribute vertical (3+ nodes) |

### Application

| Shortcut | Action |
|----------|--------|
| `Cmd/Ctrl + ,` | Open preferences / AI Assistants |
| `Cmd/Ctrl + N` | New board |
| `Cmd/Ctrl + O` | Open board |
| `Cmd/Ctrl + S` | Save (auto-save is enabled) |
| `Cmd/Ctrl + Shift + S` | Save as |

---

## Advanced Features

### History and Undo/Redo

ultramap maintains a complete operation history:

- **Undo**: `Cmd/Ctrl + Z` (reverts the last change)
- **Redo**: `Cmd/Ctrl + Shift + Z` or `Cmd/Ctrl + Y`
- **Batch Operations**: Related changes are grouped automatically
- **History Limit**: Stores recent operations (configurable)

### Board Management

#### Creating Boards

- **New Board**: `Cmd/Ctrl + N` creates a blank board
- **Auto-save**: Changes are saved automatically to the current board file

#### Opening Boards

- **Open**: `Cmd/Ctrl + O` shows a file picker
- **Recent Boards**: Access recently opened boards from the File menu
- **File Format**: Boards are stored as SQLite databases (`.db` files)

#### Saving Boards

- **Save As**: `Cmd/Ctrl + Shift + S` saves to a new location
- **File Naming**: Use descriptive names (e.g., "Project-Planning-2025.db")

### Data Storage

All data is stored locally:

- **Format**: SQLite database with foreign key constraints
- **Location**: User-selected location (via Save As)
- **Tables**:
  - `nodes`: All content nodes
  - `edges`: User and system edges
  - `embeddings`: Vector embeddings for search
  - `board_meta`: Board metadata
  - `change_history`: Operation history for undo/redo
- **Privacy**: No data is sent to external servers (embeddings are generated locally)

### Graph Analysis

ultramap treats your content as a knowledge graph:

- **Nodes**: Ideas, concepts, information
- **Edges**: Relationships (explicit and implicit)
- **Traversal**: Find connections through the graph
- **Clustering**: Detect communities of related content
- **Pathfinding**: Discover how concepts connect

These features are primarily accessible via AI assistants using MCP tools.

---

## Tips and Best Practices

### Organization

1. **Use Frames for Sections**: Group related content into frames (e.g., "Research", "Ideas", "Action Items")
2. **Color-Code by Theme**: Use consistent colors for different types of content
3. **Leverage Z-Order**: Keep background elements (frames, shapes) behind foreground content
4. **Grid Layouts**: Use the alignment tools or MCP's `organize_notes_grid` for clean layouts

### Search and Discovery

1. **Add Context**: Write descriptive content to improve semantic search
2. **Use Full Sentences**: "Project deadline is March 15" works better than "3/15 deadline"
3. **Adjust Similarity Threshold**: Lower thresholds (20-30%) find broader connections
4. **Explore System Edges**: Use AI assistants to discover auto-generated relationships

### Performance

1. **Limit Active Board Size**: Very large boards (1000+ nodes) may impact performance
2. **Create Multiple Boards**: Split projects across separate boards
3. **Use Frames**: Frames help organize large amounts of content
4. **Delete Unused Content**: Remove old nodes to keep boards focused

### AI Assistant Integration

1. **Be Specific with Positions**: Provide x,y coordinates for precise placement
2. **Describe Desired State**: "Create a grid of 6 notes starting at 100,100 with spacing 300x250"
3. **Use Node IDs**: Copy node IDs from the UI to reference specific nodes
4. **Combine Operations**: Ask the AI to create multiple nodes and connect them in one request
5. **Leverage Discovery**: Ask the AI to find patterns, clusters, or related content you might have missed

### Content Creation

1. **Start with Sticky Notes**: Quick capture during brainstorming
2. **Refine with Text Nodes**: Add clean labels and titles
3. **Add Visual Structure**: Use shapes and frames to create hierarchy
4. **Embed References**: Add website cards for research links
5. **Include Media**: YouTube cards for tutorial content or presentations

### Workflow Examples

**Brainstorming Session**:
1. Create sticky notes for all ideas (rapid capture)
2. Group related ideas into frames
3. Use semantic search to find similar content
4. Connect related concepts with edges
5. Color-code by priority or theme

**Research Project**:
1. Create website cards for reference materials
2. Add sticky notes for key insights
3. Create text nodes for summaries
4. Use frames to organize by research area
5. Use AI assistant to find thematic clusters

**Project Planning**:
1. Create frames for project phases
2. Add sticky notes for tasks within each phase
3. Create connectors to show dependencies
4. Use rectangle shapes for milestones
5. Color-code by team or priority
6. Use AI assistant to organize and optimize layout

---

## Troubleshooting

### Search Not Working

- Ensure you have created content first (embeddings are generated after content creation)
- Wait a few seconds after creating content for embeddings to process
- Check that content has meaningful text (empty or very short content may not index well)

### AI Assistant Not Connecting

1. Verify the AI assistant (Claude Desktop, ChatGPT, VS Code) is installed
2. Check that ultramap is running
3. Try manual configuration if auto-config fails
4. Restart both applications after configuration
5. Check the AI assistant's logs for MCP server errors

### Performance Issues

- Consider splitting large boards into multiple smaller boards
- Close other resource-intensive applications
- Restart ultramap periodically for long sessions
- Check system resources (RAM, CPU usage)

### Content Not Appearing

- Ensure you're in Select mode (press `V`) to interact with existing content
- Check zoom level (press `Cmd/Ctrl + 0` to fit all content)
- Use the minimap (bottom-right) to locate content on large boards
- Try searching for content to jump to its location

---

## Getting Help

### Documentation

- **This Guide**: Comprehensive user documentation
- **MCP Specification**: https://modelcontextprotocol.io
- **GitHub Repository**: Check for updates and known issues

### Community

- Report bugs and request features via the GitHub issues page
- Share tips and workflows with other users

### System Requirements

- **Operating System**: macOS 10.13+, Windows 10+, or Linux (Ubuntu 18.04+)
- **Memory**: 4GB RAM minimum, 8GB recommended
- **Storage**: 500MB for application + board data
- **Display**: 1280x720 minimum resolution

---

## Conclusion

ultramap combines the flexibility of visual thinking with the power of AI to help you organize, discover, and connect your ideas. Whether you're brainstorming, researching, planning projects, or organizing knowledge, the infinite canvas and intelligent features adapt to your workflow.

Start creating, experiment with AI assistants, and discover insights in your knowledge graph!

**Version**: 0.1.0
**Last Updated**: 2025

---
