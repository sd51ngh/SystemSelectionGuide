# 🏭 Manufacturing Software Systems Comprehensive Guide

A client-side, cryptographically secured research and evaluation portal for **128 manufacturing software systems** across **ERP, MRP, MES, QMS, APS, CMMS, SCADA, IIoT, Connected Worker, and Field Service** categories. Compiled from industry review platforms (**Capterra**, **G2**, **Gartner**, **IDC**) and direct UK vendor/reseller intelligence.

---

## ✨ Key Features

- **🔐 Cryptographic Access Control**: Uses Web Crypto API (`PBKDF2` with 100,000 SHA-256 iterations + `AES-256-GCM`) to decrypt the embedded vendor database directly in the browser without requiring a backend server (works seamlessly over `file://` or static hosting).
- **🗂️ Interactive Grid & 📊 Market Position Chart**:
  - **Grid View**: Detailed vendor cards displaying target company size, deployment model, financial stability rating, UK support level (`UK Native`, `UK Support`, `Global Support`), industry sectors, core strengths, contact details, and UK Value-Added Resellers (VARs).
  - **Market Position Chart**: Interactive zoomable/pannable SVG bubble chart mapping vendors across *Capabilities*, *Strategies*, and *Market Share* (`Leaders`, `Major Players`, `Contenders`, `Participants`).
- **🔍 Multi-Dimensional Filtering**:
  - Instant free-text search by vendor name, strength, or description.
  - Multi-select filter dropdowns for **19 Manufacturing Sectors** and **17 Software Categories**.
  - Single-click filters for **Company Size** (`Small`, `Mid-Market`, `Enterprise`), **UK Support Presence**, and **Financial Stability**.
- **📝 Local Evaluation Notes & Custom Vendors**:
  - Add, edit, and persist custom evaluation notes for both individual systems and their UK VARs (stored locally in `localStorage`, with custom vendor additions encrypted via the session key).
  - Automatic merging of newly added default systems into any existing cached `localStorage` vendor list.
- **📤 / 📥 Data Portability**:
  - **JSON**: Export or import the full vendor database (`data.json`).
  - **CSV**: RFC 4180-compliant export and import of system and VAR evaluation notes.
  - **Markdown (`.md`)**: Structured Markdown export and import of evaluation notes.
- **🌗 Dark / Light Theme**: Persistent theme toggle with automatic system preference detection.

---

## 📊 Database Coverage (128 Systems — Updated November 2026)

### Categories Covered
| Category | Examples |
| :--- | :--- |
| **Enterprise & Mid-Market Cloud ERP** | SAP S/4HANA, SAP Business One, Oracle NetSuite, Microsoft Dynamics 365, IFS Cloud, EPICOR Kinetic, Infor CloudSuite Industrial, Acumatica, SYSPRO, QAD, Rootstock, Priority ERP, Access SupplyChain, RamBase, Abas ERP |
| **UK SME & Job Shop MRP/ERP** | 123 Insight, Access FactoryMaster, WinMan ERP, EFACS E/8, Fit Factory (Tricorn), ProgressPlus, Cim50, E-Max ERP, Redthorn MRP, OrderWise, PSL Datatrack, Fraction ERP, Statii, Flowlens, MIE Track Pro, Pegasus Opera 3, Intact iQ, JobBOSS², ECI M1, ProShop ERP, Fulcrum Pro, Genius ERP, Cetec ERP, Herbst Insight |
| **Cloud Inventory & Open-Source MRP** | Katana MRP, MRPeasy, Unleashed, Cin7 Core, Fishbowl Manufacturing, Odoo Manufacturing, ERPNext |
| **Process, Batch, Food & Chemical ERP** | Aptean Industrial & Food ERP (Sanderson), Deacom ERP, BatchMaster Manufacturing, Formpak, Datacor ERP, Wherefour, Mar-Kov, Xybion LIMS + ERP |
| **Advanced Planning & Scheduling (APS)** | Access Orchestrate, PlanetTogether APS, Siemens Opcenter APS |
| **Manufacturing Execution Systems (MES)** | DELMIAWorks (IQMS), Rockwell FactoryTalk MES, Critical Manufacturing MES, Siemens Opcenter, Plex, GE Digital Proficy, Aegis FactoryLogix, Seiki Systems, Harford Control, V5 Traceability, Total Control Pro (DynamxMFG), Autodesk Fusion Operations (Prodsmart), NoMuda VisualFactory, FORCAM Force, Sepasoft, Shoplogix |
| **Quality Management Systems (QMS)** | Ideagen Q-Pulse, Ideagen Quality Management (iQMS), MasterControl, ETQ Reliance (Hexagon), Veeva Vault QMS, ComplianceQuest, Pilgrim SmartSolve (IQVIA), Qualio, Intelex EHSQ |
| **Maintenance & Asset Management (CMMS)** | Fiix CMMS (Rockwell Automation), MaintainX, Limble CMMS |
| **IIoT, Machine Monitoring, SCADA & Connected Worker** | Ignition, AVEVA System Platform, PTC ThingWorx, FourJaw, Busroot, Brainboxes, Factbird, MachineMetrics, Scytec DataXchange, Redzone, Tulip, VKS, Azumuta, Poka / Operations1, Starling, GembaDocs |
| **Field Service Management (FSM)** | ServiceMax (PTC), simPRO, BigChange, Joblogic, Aeromark SAM, EAGLE Field Service, Jobber |

### Manufacturing Sectors Supported
- 💊 Pharma (`pharma`)
- 🍔 Food & Beverage (`food`)
- 🔶 Plastic (`plastic`)
- 🔧 Precision Engineering (`precision`)
- 📱 Electronics (`electronics`)
- 🚗 Automotive (`automotive`)
- ✈️ Aerospace (`aerospace`)
- 🧪 Chemicals (`chemicals`)
- ⚕️ Medical Devices (`medical`)
- 🏭 Industrial (`industrial`)
- 🔬 Biotech (`biotech`)
- 🔩 Metals & Fabrication (`metals_fabrication`)
- 🧵 Textiles & Apparel (`textiles_apparel`)
- 🪚 Woodworking & Furniture (`woodworking_furniture`)
- 📦 Printing & Packaging (`printing_packaging`)
- 🛡️ Defense & Security (`defense_security`)
- ⚡ Renewable Energy & Cleantech (`renewable_energy`)
- 🛍️ Consumer Goods (`consumer_goods`)
- 💄 Cosmetics (`cosmetics`)

---

## 🚀 Quick Start

1. Open `index.html` directly in any modern browser (Chrome, Edge, Firefox, Safari) or serve the directory over a local static server.
2. Log in at the **Secure Access Portal** using your authorized WMG SME credentials.
3. Use the search bar, sector/category multi-select dropdowns, or switch to the **Market Position Chart** to explore systems.

---

## 🛠️ Project Structure

```text
ERPguide/
├── index.html            # Main application shell, login portal, filters, and modal layout
├── styles.css            # Responsive light/dark theme styling, grid cards, and SVG chart styles
├── app.js                # Core application logic + AES-256-GCM encrypted default database
├── data.json             # Plaintext JSON source database (128 manufacturing systems)
├── README.md             # Project documentation and maintenance guide
├── AGENTS.md             # Workspace rules for AI coding assistants
├── convert_xlsx.py       # Legacy utility to convert Excel spreadsheets to JSON
├── restructure_json.py   # Legacy utility to normalize spreadsheet headers
└── clean_json.py         # Legacy utility to strip NaN/null values from JSON
```

---

## 🔄 Updating the Encrypted Database in `app.js`

Whenever `data.json` is modified, re-encrypt and inline the updated dataset into `ENCRYPTED_DATABASE` in `app.js` using Node.js:

```powershell
node -e "const fs = require('fs'); const crypto = require('crypto'); const plaintext = fs.readFileSync('data.json', 'utf8'); JSON.parse(plaintext); const salt = crypto.randomBytes(16); const iv = crypto.randomBytes(12); const key = crypto.pbkdf2Sync('<USERNAME>:<PASSWORD>', salt, 100000, 32, 'sha256'); const cipher = crypto.createCipheriv('aes-256-gcm', key, iv); const ciphertext = Buffer.concat([cipher.update(plaintext, 'utf8'), cipher.final()]); const tag = cipher.getAuthTag(); const encObj = { salt: salt.toString('hex'), iv: iv.toString('hex'), tag: tag.toString('hex'), ciphertext: ciphertext.toString('hex') }; let appJs = fs.readFileSync('app.js', 'utf8'); appJs = appJs.replace(/const ENCRYPTED_DATABASE = \{[\s\S]*?\};/, 'const ENCRYPTED_DATABASE = ' + JSON.stringify(encObj, null, 2) + ';'); fs.writeFileSync('app.js', appJs, 'utf8');"
```

