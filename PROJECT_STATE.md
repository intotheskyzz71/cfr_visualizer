# CFR Visualizer - Project State Document

## Project Overview
**CFR Visualizer v3.0** is a web-based money flow investigation tool designed for analyzing financial transaction data and visualizing account relationships through interactive network graphs. The application is specifically tailored for forensic financial analysis with Thai language support.

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

### 1. User Interface (`cfr-visualizer.html:280-366`)
- **Header**: File upload controls, analyze button, version badge
- **Main Content**: Network visualization container
- **Controls Overlay**: Zoom in/out, fit to screen, reset buttons
- **Loading Overlay**: Processing indicator
- **Tooltip System**: Interactive node information display

### 2. Core Modules

#### Application State (`cfr-visualizer.html:371-380`)
```javascript
const app = {
    data: null,           // Uploaded file data
    network: null,        // Processed network data
    simulation: null,     // D3 force simulation
    zoom: null,          // D3 zoom behavior
    svg: null,           // Main SVG element
    g: null,             // Main group element
    pinnedNode: null     // Currently pinned tooltip node
}
```

#### Utility Functions (`cfr-visualizer.html:382-519`)
- **Date/Time Parsing**: Supports Thai Buddhist calendar, Excel serial dates, various formats
- **Amount Processing**: Currency parsing and formatting
- **Thai Language Support**: Number conversion, month names
- **Data Validation**: Input sanitization and type conversion

#### Network Visualization (`cfr-visualizer.html:521-1049`)
- **Hierarchical Layout**: Layer-based node positioning starting from victim accounts
- **Interactive Network**: Drag, zoom, pan functionality
- **Curved Links**: Aesthetic transaction flow representation
- **Tooltip System**: Hover and click-to-pin node information
- **Visual Encoding**: Different node types (victim, intermediate, regular)

#### Data Processing (`cfr-visualizer.html:1051-1194`)
- **File Reading**: Excel/CSV parsing with error handling
- **Transaction Processing**: Data cleaning and timestamp ordering
- **Network Building**: Node and link aggregation from transaction data

#### UI Controllers (`cfr-visualizer.html:1196-1267`)
- **Event Handling**: File upload, button interactions
- **Loading States**: Progress indication during processing
- **Reset Functionality**: Application state cleanup

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
1. **File Upload** → Raw spreadsheet data extraction
2. **Data Cleaning** → Column name normalization, type conversion
3. **Transaction Processing** → Date/time parsing, amount normalization
4. **Network Building** → Node creation, link aggregation, statistics calculation
5. **Layout Calculation** → Hierarchical layer assignment using BFS algorithm
6. **Visualization Rendering** → D3.js network graph generation

## Key Features

### Visualization Features
- **Layered Layout**: Automatic hierarchical arrangement from victim accounts
- **Interactive Nodes**: Hover tooltips, click-to-pin information
- **Curved Links**: Weighted by transaction amount, directional arrows
- **Draggable Elements**: Nodes and layer labels repositionable
- **Zoom Controls**: Pan, zoom, fit-to-screen functionality

### Data Features
- **Multi-format Support**: Excel (.xlsx, .xls) and CSV files
- **Thai Localization**: Buddhist calendar, Thai numerals, month names
- **Transaction Aggregation**: Multiple transactions between same accounts
- **Victim Identification**: First transaction source marked as victim
- **Statistics Calculation**: Total in/out amounts, transaction counts per node

### User Experience
- **Single-file Deployment**: No installation or server required
- **Responsive Design**: Adapts to different screen sizes  
- **Error Handling**: Graceful failure with user feedback
- **Loading States**: Progress indication for long operations

## Current State

### Completed Features ✅
- Complete single-file application architecture
- Full Thai language support and localization
- Interactive network visualization with D3.js
- Excel/CSV file processing with SheetJS
- Hierarchical layout algorithm
- Drag and zoom functionality
- Tooltip system with pin capability
- Transaction aggregation and statistics
- Date/time parsing for multiple formats
- Visual distinction for victim accounts

### Technical Debt & Improvements Needed
- **Code Organization**: Consider modularizing the large single file
- **Performance**: Large datasets may cause browser slowdowns
- **Accessibility**: Missing ARIA labels and keyboard navigation
- **Mobile Support**: Touch interactions could be improved
- **Error Reporting**: More detailed error messages for data issues
- **Export Features**: No capability to save or export visualizations
- **Data Validation**: Limited input validation and user guidance

### Browser Compatibility
- **Recommended**: Chrome, Firefox, Edge (modern versions)
- **Dependencies**: Requires JavaScript enabled, stable internet for CDN libraries
- **File Handling**: Uses HTML5 FileReader API

## Development Notes
- Version: 3.0 (as indicated in UI badge)
- License: MIT (as stated in README)
- Language: Thai (primary UI language)
- Last modified: Recent commits show README updates and HTML file changes

This project represents a specialized forensic analysis tool with a focus on simplicity, portability, and Thai market needs.