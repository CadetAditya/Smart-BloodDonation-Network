# 🩸 Smart Blood Donation Network

[![Live Demo](https://img.shields.io/badge/Live_Demo-Open_in_Browser-E11D48?style=for-the-badge&logo=googlechrome&logoColor=white)](https://cadetaditya.github.io/Smart-BloodDonation-Network/docs/)
![Java](https://img.shields.io/badge/Java-8%20to%2025-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![Swing](https://img.shields.io/badge/GUI-Java%20Swing-blue?style=for-the-badge)
![WebAssembly](https://img.shields.io/badge/WebAssembly-CheerpJ%203.0-654FF0?style=for-the-badge)
![DSA](https://img.shields.io/badge/Architecture-Data%20Structures%20%26%20Algorithms-crimson?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

A modern, high-performance desktop blood bank and emergency matching network built with **Java Swing** and custom dark-themed UI components. The system is engineered around core **Data Structures & Algorithms (DSA)** to guarantee $\mathcal{O}(1)$ donor lookups, prioritized emergency resolution, and multi-structure rollback operations.

> 🌐 **Live In-Browser Demo**: You can run and interact with the full Java Swing desktop GUI directly in your web browser via WebAssembly (CheerpJ 3.0) without installing Java:  
> **👉 [Launch Live App in Browser](https://cadetaditya.github.io/Smart-BloodDonation-Network/docs/)**  
> *(Admin credentials — Username: `admin` | Password: `password`)*

---

## 🌟 Key Features

* **⚡ O(1) Hierarchical Search Indexing**: Nested maps (`BloodGroup -> City -> List<Donor>`) for instant compatibility queries without linear database scanning.
* **🚨 Priority-Driven Emergency Queue**: Min/max binary heap prioritizing critical life-saving demands before standard requests.
* **🔄 Multi-Structure Undo Stack**: Command Pattern implementation that rolls back changes synchronously across donor registries, nested indices, priority queues, and ledgers.
* **🛡️ Unique Constraint Enforcements**: Fast phone-based uniqueness verification in $\mathcal{O}(1)$ time.
* **⏳ 90-Day Medical Eligibility Rule**: Automated date algebra ensuring donors strictly meet safe donation intervals.
* **🎨 Modern Dark Design System**: Sleek custom Swing UI (rounded cards, smooth hover effects, custom tables, and responsive forms).
* **👤 Public Self-Registration Portal**: Allows voluntary donors to register themselves directly from the authentication screen without administrative privileges.

---

## 🏗️ Architecture & Data Structures (DSA)

| Feature | Data Structure / Pattern | Time Complexity | Purpose |
| :--- | :--- | :--- | :--- |
| **Donor ID Lookup** | `HashMap<Integer, Donor>` | $\mathcal{O}(1)$ | Primary key access for donor records |
| **Phone Validation** | `HashMap<String, Donor>` | $\mathcal{O}(1)$ | Unique phone constraint verification |
| **Search Index** | `HashMap<String, HashMap<String, ArrayList<Donor>>>` | $\mathcal{O}(1)$ | Indexed blood group & location filtering |
| **Emergency Queue** | `PriorityQueue<Request>` | $\mathcal{O}(\log N)$ | Urgency heap with timestamp tie-breaking |
| **Donation History** | `LinkedList<Donation>` | $\mathcal{O}(1)$ | Sequential audit trail of completed matches |
| **Undo Engine** | `Stack<Action>` | $\mathcal{O}(1)$ | Command Pattern multi-level rollback |
| **Compatibility Rule** | Medical Matrix Mapping | $\mathcal{O}(1)$ | ABO & Rh factor compatibility logic |

For complete code snippets and viva/report explanations, see [DSA_DOCUMENTATION.md](DSA_DOCUMENTATION.md).

---

## 🚀 Getting Started

### Prerequisites
* **Java Development Kit (JDK) 8 or higher** (JDK 17+ recommended).

### Running the Application

#### Windows (PowerShell):
```powershell
.\run.ps1
```

#### Windows (CMD / Batch):
```bat
run.bat
```

#### Manual Compilation & Run:
```bash
# 1. Compile source files into bin/
javac -d bin src/App.java src/model/*.java src/service/*.java src/ui/*.java src/ui/components/*.java

# 2. Run the application
java -cp bin App
```

---

## 🔐 Default Credentials

| Portal | Username | Password |
| :--- | :--- | :--- |
| **Admin Dashboard** | `admin` | `password` |
| **Donor Registration** | *No login required (Direct access from Login screen)* |

---

## 📁 Project Structure

```
Smart Blood donation/
├── run.bat / run.ps1                 # Automated launch scripts
├── DSA_DOCUMENTATION.md             # DSA technical reference
├── README.md                        # Project documentation
└── src/
    ├── App.java                     # Application entry point
    ├── model/                       # Domain entities & Command Pattern actions
    │   ├── Action.java
    │   ├── AddDonorAction.java
    │   ├── AssignDonorAction.java
    │   ├── DeleteDonorAction.java
    │   ├── UpdateDonorAction.java
    │   ├── Donation.java
    │   ├── Donor.java
    │   ├── Priority.java
    │   └── Request.java
    ├── service/                     # Central business logic & index manager
    │   └── BloodBankManager.java
    └── ui/                          # GUI presentation layer
        ├── MainFrame.java
        ├── LoginPanel.java
        ├── PublicRegisterPanel.java
        ├── DashboardPanel.java
        ├── DonorPanel.java
        ├── RequestPanel.java
        ├── QueuePanel.java
        ├── SearchPanel.java
        ├── HistoryPanel.java
        ├── UndoPanel.java
        └── components/              # Reusable UI component library
```

---

## 📄 License
This project is open-source and available under the [MIT License](LICENSE).

