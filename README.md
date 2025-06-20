# CFR Visualizer

**Enhanced Money Flow Investigation Tool**

CFR Visualizer is a professional web-based application for visualizing and investigating money flow from financial transaction data. It supports multiple Excel and CSV inputs and generates an interactive network graph with advanced features for forensic financial analysis.

## 🚀 Key Features

### 🎯 **Advanced Network Visualization**
* **Multi-layer Hierarchical Layout**: Automatically arranges nodes starting from victim accounts with collision avoidance
* **Interactive Context Menus**: Right-click nodes for theme selection and management options
* **Node Theme System**: 4 color categories (Dark, Red, Yellow, Gray) for visual classification
* **Manual Node Management**: Delete and restore nodes for focused analysis
* **Enhanced Link Rendering**: Dynamic curved paths with overlap prevention
* **Professional Tooltips**: Hover and click-to-pin detailed node information

### 📁 **Multi-File Processing**
* **Simultaneous File Upload**: Process multiple Excel/CSV files at once
* **Multi-Source Analysis**: Support for multiple root victim accounts
* **Unified Network View**: Integrated visualization from all uploaded files

### 🛠️ **Professional Tools**
* **Advanced Controls**: Zoom, pan, fit-to-screen with enhanced precision
* **Developer Contact**: Integrated contact modal for support
* **Thai Localization**: Full support for Thai language and Buddhist calendar
* **Data Validation**: Comprehensive input validation and error handling

## 📁 Project Structure

```
cfr-visualizer/
├── cfr-visualizer.html    # Main application file (single-file architecture)
├── README.md              # Project documentation
└── PROJECT_STATE.md       # Detailed technical documentation
```

> **Note**: All functionality is contained within `cfr-visualizer.html` for maximum portability and ease of deployment.

## 🛠️ Technologies Used

* **D3.js** (v7.8.5) for advanced data visualization and network layouts
* **SheetJS (xlsx.js)** (v0.18.5) for comprehensive Excel and CSV file processing
* **HTML5 & CSS3** with Google Fonts (Inter, Sarabun) for professional UI
* **Vanilla JavaScript** (ES6+) with modular architecture for optimal performance

## 🔧 Installation & Usage

### Quick Start
1. **Download**: Clone or download `cfr-visualizer.html`
2. **Open**: Launch the file in any modern web browser
3. **Upload**: Select multiple `.xlsx`, `.xls`, or `.csv` transaction files
4. **Analyze**: Click **วิเคราะห์** (Analyze) to generate the network
5. **Explore**: Use advanced features via context menus and controls

### Detailed Steps
```bash
# Clone the repository
git clone https://github.com/<your-username>/cfr-visualizer.git

# Navigate to project
cd cfr-visualizer

# Open in browser (Chrome, Firefox, Edge recommended)
open cfr-visualizer.html
```

## 🗂️ Input Data Format

Your spreadsheet files should contain these columns:

| Column Name            | Description                                 | Required |
| ---------------------- | ------------------------------------------- | -------- |
| `transfer_date`        | Transaction date (multiple formats supported) | ✅ |
| `transfer_time`        | Transaction time (HH:MM or Excel fraction) | ✅ |
| `from_bank_short_name` | Source bank code/name                      | ✅ |
| `from_account_no`      | Source account number                      | ✅ |
| `from_account_name`    | Source account holder name                 | ⚪ |
| `to_bank_short_name`   | Target bank code/name                      | ✅ |
| `to_account_no`        | Target account number                      | ✅ |
| `to_account_name`      | Target account holder name                 | ⚪ |
| `to_id`                | Target personal ID                         | ⚪ |
| `transfer_amount`      | Transaction amount (numeric, with currency) | ✅ |
| `transfer_description` | Transaction description or remarks         | ⚪ |

### Supported Date Formats
- Thai Buddhist calendar (e.g., "13 มีนาคม 2568")
- Standard formats (DD/MM/YYYY, YYYY-MM-DD)
- Excel serial dates
- ISO date strings

## 🎮 Advanced Controls & Interaction

### Basic Navigation
* **Zoom**: Mouse wheel or zoom buttons
* **Pan**: Click and drag on empty space
* **Fit to Screen**: Auto-center and scale all nodes
* **Reset**: Clear current analysis and reload

### Context Menu Features (Right-Click on Nodes)
* **Theme Selection**: Choose from 4 color categories
  - **Dark** (●): Default categorization
  - **Red** (●): High-priority or suspicious accounts
  - **Yellow** (●): Medium-priority or flagged accounts  
  - **Gray** (●): Low-priority or inactive accounts
* **Node Management**: Delete or restore nodes for focused analysis

### Professional Features
* **Contact Support**: Click the question mark icon in the top-right corner
* **Multi-File Analysis**: Upload multiple files for comprehensive investigation
* **Persistent Tooltips**: Click nodes to pin detailed information
* **Layer Management**: Drag layer labels to reorganize hierarchy

## 👮 Law Enforcement Features

This tool is specifically designed for financial crime investigation:

* **Multi-Victim Support**: Analyze cases with multiple victim accounts
* **Visual Classification**: Color-code accounts by investigation priority
* **Transaction Flow Analysis**: Clear visualization of money movement patterns
* **Professional Documentation**: Export-ready visualizations for case files
* **Thai Government Compatibility**: Full Thai language and calendar support

## 🤝 Contributing

We welcome contributions from the law enforcement and forensic accounting communities:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/YourFeature`)
3. **Commit** your changes (`git commit -m "Add forensic feature"`)
4. **Push** to the branch (`git push origin feature/YourFeature`)
5. **Open** a Pull Request with detailed description

## 📞 Contact & Support

For technical support, feature requests, or law enforcement collaboration:

* **Developer**: ร.ต.อ.พลวัฒน์ วิริยะโชติวิบูล
* **Position**: รอง สว.(สอบสวน) กก.3 บก.สอท.1
* **Phone**: 086-445-9351
* **LINE ID**: bpp9351

*Contact information is also available via the in-app contact button (? icon)*

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🔗 Technical Documentation

For detailed technical specifications, see [PROJECT_STATE.md](PROJECT_STATE.md)

---

**CFR Visualizer** - Professional Financial Crime Investigation Tool  
*Developed for Thai Law Enforcement by ร.ต.อ.พลวัฒน์ วิริยะโชติวิบูล*