# CFR Visualizer v3

**Enhanced Money Flow Investigation Tool**

CFR Visualizer is a web-based application for visualizing and investigating money flow from financial transaction data. It supports Excel and CSV inputs and generates an interactive network graph to explore transactions across bank accounts.

## 🚀 Features

- **Interactive Network Graph**: Visualize account entities as nodes and transactions as curved, weighted links.
- **Layered Layout**: Automatically arranges nodes in layers starting from victim accounts, enabling clear hierarchical investigation.
- **Rich Tooltips**: Hover and click on nodes to see detailed information including total in/out amounts, transaction counts, and personal details.
- **Drag & Zoom**: Pan, zoom, and reposition both nodes and layer labels for customized exploration.
- **Date & Time Parsing**: Supports various date/time formats, including Thai Buddhist calendar, Excel serial dates, and standard ISO formats.
- **Multi-language Labels**: Labels and UI are localized in Thai (configurable).

## 📁 Project Structure

```
├── index.html        # Main HTML file with embedded CSS & JavaScript
├── styles/           # (Optional) External styles if separated
├── scripts/          # (Optional) Separated JS modules
└── assets/           # (Optional) Icons, fonts, images
```

> Note: In this version (v3.0), all code is bundled within `index.html` for simplicity.

## 🛠️ Technologies Used

- **D3.js** (v7.x) for data-driven document visualization and force layout management.
- **SheetJS (xlsx.js)** for reading Excel (`.xlsx`, `.xls`) and CSV files in-browser.
- **HTML5 & CSS3** with Google Fonts (Inter, Sarabun) for UI styling.
- **Vanilla JavaScript** (ES6+) with modular structure for data processing and network rendering.

## 🔧 Installation & Usage

1. Clone the repository:
   ```bash
   git clone https://github.com/<your-username>/cfr-visualizer.git
   ```
2. Navigate into the project folder:
   ```bash
   cd cfr-visualizer
   ```
3. Open `index.html` in your browser (Chrome, Firefox, Edge recommended):
   ```bash
   open index.html
   ```
4. Click **เลือกไฟล์** (Choose File) and select your `.xlsx`, `.xls`, or `.csv` bank transaction file.
5. Click **วิเคราะห์** (Analyze) to generate the money flow network.
6. Use zoom, pan, and drag controls to explore the graph.

## 🗂️ Input Data Format

Your spreadsheet should contain these columns (headers are case-sensitive):

| Column Name            | Description                                 |
| ---------------------- | ------------------------------------------- |
| `transfer_date`        | Transaction date (Excel serial or text)     |
| `transfer_time`        | Transaction time (hh\:mm or Excel fraction) |
| `from_bank_short_name` | Source bank code/name                       |
| `from_account_no`      | Source account number                       |
| `from_account_name`    | Source account holder name (optional)       |
| `to_bank_short_name`   | Target bank code/name                       |
| `to_account_no`        | Target account number                       |
| `to_account_name`      | Target account holder name (optional)       |
| `to_id`                | Target personal ID (optional)               |
| `transfer_amount`      | Transaction amount (numeric, with currency) |
| `transfer_description` | Description or remarks (optional)           |

> *Ensure that your date columns use consistent formats. The app will attempt to parse Thai months and Buddhist years.*

## 🎮 Controls & Interaction

- **Zoom In / Zoom Out**: Use the overlay buttons or mouse wheel to adjust scale.
- **Pan**: Click and drag on empty space of the graph.
- **Fit to Screen**: Center and zoom to fit all nodes.
- **Reset**: Clear the current network and reload file input.
- **Tooltip**: Hover over a node to see summary; click to pin.
- **Layer Labels**: Drag the layer labels to reposition hierarchy annotations.

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repo.
2. Create a new branch (`git checkout -b feature/YourFeature`).
3. Commit your changes (`git commit -m "Add YourFeature"`).
4. Push to the branch (`git push origin feature/YourFeature`).
5. Open a Pull Request.

## 📄 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

