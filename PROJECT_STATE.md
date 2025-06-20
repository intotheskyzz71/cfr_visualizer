# CFR Visualizer - Project State Document

## Project Overview
**CFR Visualizer** is a web-based money flow investigation tool designed for analyzing financial transaction data and visualizing account relationships through interactive network graphs. The application is specifically tailored for forensic financial analysis with Thai language support and advanced user interaction features.

## Project Structure
```
cfr-visualizer/
├── README.md              # Project documentation and usage instructions
├── cfr-visualizer.html     # Main application file (single-file architecture)
└── PROJECT_STATE.md        # This document
```

## Architecture

### Single-File Architecture
The entire application is contained within `cfr-visualizer.html` for simplicity and portability. The file contains:
- HTML structure and UI components
- Embedded CSS styling
- Complete JavaScript application logic
- External library dependencies via CDN

### Core Technologies
- **D3.js v7.8.5**: Data visualization and force layout management
- **SheetJS (xlsx.js) v0.18.5**: Excel and CSV file parsing
- **HTML5 & CSS3**: UI framework with Google Fonts (Inter, Sarabun)
- **Vanilla JavaScript (ES6+)**: Application logic with modular structure

## Application Components

### 1. User Interface (`cfr-visualizer.html:430-647`)
- **Header**: File upload controls (multi-file support), analyze button, contact button
- **Main Content**: Network visualization container with enhanced layout
- **Context Menu**: Right-click node menu for color themes and deletion
- **Contact Modal**: Developer contact information popup
- **Loading Overlay**: Processing indicator
- **Tooltip System**: Interactive node information display

### 2. Core Modules

#### Application State (`cfr-visualizer.html:555-572`)
```javascript
const app = {
    data: [],                    // Multiple uploaded files support
    network: null,               // Processed network data
    simulation: null,            // D3 force simulation
    zoom: null,                 // D3 zoom behavior
    svg: null,                  // Main SVG element
    g: null,                    // Main group element
    pinnedNode: null,           // Currently pinned tooltip node
    currentTheme: 'dark',       // Default node theme
    deletedNodes: new Set(),    // Track deleted nodes
    contextMenu: {              // Context menu state
        visible: false,
        targetNode: null,
        x: 0, y: 0
    }
}
```

#### Utility Functions (`cfr-visualizer.html:382-519`)
- **Date/Time Parsing**: Supports Thai Buddhist calendar, Excel serial dates, various formats
- **Amount Processing**: Currency parsing and formatting
- **Thai Language Support**: Number conversion, month names
- **Data Validation**: Input sanitization and type conversion

#### Network Visualization (`cfr-visualizer.html:707-1376`)
- **Enhanced Hierarchical Layout**: Multi-row layer support with collision avoidance
- **Advanced Link Rendering**: Dynamic curve calculation with overlap prevention
- **Interactive Network**: Drag, zoom, pan functionality with improved spacing
- **Context Menu System**: Right-click menus for node customization
- **Theme System**: 4 color themes (dark, red, yellow, gray) for node categorization
- **Node Management**: Manual deletion and restoration capabilities
- **Tooltip System**: Hover and click-to-pin node information

#### Data Processing (`cfr-visualizer.html:1378-1530`)
- **Multi-File Reading**: Support for multiple Excel/CSV files simultaneously
- **Enhanced Transaction Processing**: Improved data cleaning and timestamp ordering
- **Advanced Network Building**: Multi-source victim identification and link aggregation

#### UI Controllers (`cfr-visualizer.html:1690-1820`)
- **Enhanced Event Handling**: Multi-file upload, context menu, modal interactions
- **Contact System**: Developer contact modal with professional information
- **Context Menu Management**: Theme selection and node deletion via right-click
- **Loading States**: Enhanced progress indication during processing
- **Reset Functionality**: Comprehensive application state cleanup

## Data Flow

### Input Requirements
The application expects spreadsheet data with these columns:
- `transfer_date`: Transaction date (multiple formats supported)
- `transfer_time`: Transaction time (HH:MM or Excel fraction)
- `from_bank_short_name`: Source bank code
- `from_account_no`: Source account number
- `from_account_name`: Source account holder name (optional)
- `to_bank_short_name`: Target bank code
- `to_account_no`: Target account number
- `to_account_name`: Target account holder name (optional)
- `to_id`: Target personal ID (optional)
- `transfer_amount`: Transaction amount (numeric with currency)
- `transfer_description`: Transaction description (optional)

### Processing Pipeline
1. **Multi-File Upload** → Support for multiple spreadsheet data extraction
2. **Data Cleaning** → Column name normalization, type conversion
3. **Enhanced Transaction Processing** → Date/time parsing, amount normalization, file indexing
4. **Advanced Network Building** → Multi-source node creation, link aggregation, statistics calculation
5. **Improved Layout Calculation** → Enhanced hierarchical layer assignment with row splitting
6. **Advanced Visualization Rendering** → D3.js network graph with collision avoidance and enhanced curves

## Key Features

### Visualization Features
- **Enhanced Layered Layout**: Automatic hierarchical arrangement with multi-row support
- **Interactive Nodes**: Hover tooltips, click-to-pin information, right-click context menus
- **Advanced Curved Links**: Dynamic curve calculation, collision avoidance, weighted by amount
- **Theme System**: 4 visual themes for node categorization (dark, red, yellow, gray)
- **Node Management**: Manual deletion and restoration capabilities
- **Draggable Elements**: Nodes and layer labels repositionable
- **Enhanced Zoom Controls**: Pan, zoom, fit-to-screen functionality

### Data Features
- **Multi-file Support**: Process multiple Excel (.xlsx, .xls) and CSV files simultaneously
- **Thai Localization**: Buddhist calendar, Thai numerals, month names
- **Advanced Transaction Aggregation**: Multi-source transaction processing
- **Multi-Victim Identification**: Support for multiple root nodes from different files
- **Comprehensive Statistics**: Total in/out amounts, transaction counts per node
- **Data Validation**: Enhanced input validation and error reporting

### User Experience
- **Single-file Deployment**: No installation or server required
- **Professional Contact System**: Integrated developer contact modal
- **Context Menu Interface**: Modern right-click interactions
- **Enhanced Error Handling**: Graceful failure with detailed user feedback
- **Improved Loading States**: Better progress indication for long operations
- **Accessibility**: Improved keyboard navigation and screen reader support

## Current State

### Completed Features ✅
- Complete single-file application architecture
- Full Thai language support and localization
- Advanced interactive network visualization with D3.js
- Multi-file Excel/CSV processing with SheetJS
- Enhanced hierarchical layout algorithm with collision avoidance
- Advanced drag and zoom functionality with improved spacing
- Context menu system for node customization
- Theme system with 4 color categories
- Node deletion and restoration capabilities
- Contact modal system with developer information
- Professional tooltip system with pin capability
- Multi-source transaction aggregation and statistics
- Enhanced date/time parsing for multiple formats
- Visual distinction for victim accounts with multi-root support

### Technical Debt & Improvements Needed
- **Code Organization**: Consider modularizing the large single file
- **Performance**: Large datasets (>1000 nodes) may cause browser slowdowns
- **Mobile Support**: Touch interactions for context menus could be improved
- **Export Features**: No capability to save or export visualizations
- **Advanced Analytics**: Limited statistical analysis and reporting features
- **Undo/Redo**: No undo functionality for node deletions or theme changes
- **Search/Filter**: No search capability for specific nodes or transactions

### Browser Compatibility
- **Recommended**: Chrome, Firefox, Edge (modern versions)
- **Dependencies**: Requires JavaScript enabled, stable internet for CDN libraries
- **File Handling**: Uses HTML5 FileReader API

## Development Notes
- Version: Latest (version badge removed for cleaner UI)
- License: MIT (as stated in README)
- Language: Thai (primary UI language)
- Developer Contact: Integrated into application via contact modal
- Last modified: Enhanced with advanced features including context menus, themes, and multi-file support

## Contact Information
- **Developer**: ร.ต.อ.พลวัฒน์ วิริยะโชติวิบูล
- **Position**: รอง สว.(สอบสวน) กก.3 บก.สอท.1
- **Phone**: 086-445-9351
- **LINE ID**: bpp9351

This project represents a specialized forensic analysis tool with focus on advanced user interaction, visual categorization, and professional law enforcement needs in Thailand.