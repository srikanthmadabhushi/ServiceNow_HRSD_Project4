# ServiceNow_HRSD_Project4
ServiceNow HRSD – HR Case Auto-Categorization &amp; Assignment Flow
# 🚀 ServiceNow HRSD – HR Case Auto-Categorization & Assignment Flow

## 📖 Project Overview
This project automates the HR Case categorization, assignment, and resolution process using **ServiceNow HR Service Delivery (HRSD)**.  
The flow leverages **Decision Tables** and **Flow Designer** to intelligently analyze case descriptions, assign them to the correct HR team, and automatically update the case state.

---

## 🧠 Problem Statement
Manual triaging of HR cases is time-consuming and error-prone.  
HR teams often receive generic case submissions such as:
- “Need time off next week”
- “Bonus not credited”
- “Need help with salary adjustment”

Each requires routing to the correct HR team (Leave, Payroll, General HR).

---

## 💡 Solution
Using ServiceNow’s **Decision Table + Flow Designer**, this automation:
1. Reads the HR Case **Short Description**
2. Determines the **HR Category** (e.g., Time Off, Compensation, General)
3. Assigns the case to the appropriate **HR Group**
4. Optionally **auto-resolves** the case for demonstration purposes

---

## ⚙️ Tech Specs
| Component | Configuration |
|:--|:--|
| **Platform** | ServiceNow Yokohama |
| **Module** | HR Service Delivery (HRSD) |
| **Table** | `sn_hr_core_case` |
| **Decision Table Inputs** | Short Description (String) |
| **Decision Table Outputs** | HR Category (String), Assignment Group (Reference → sys_user_group) |
| **Flow Designer Trigger** | Record Created or Updated on HR Case |
| **Flow Actions** | Run Decision Table → Branch → Update Record → Auto Resolve |

---
## 🧾 Decision Table Configuration
| Rank | Condition (Short Description) | HR Category | Assignment Group |
|:--|:--|:--|:--|
| 1 | contains "time off" | Time Off | HR Leave Team |
| 2 | contains "bonus" | Compensation | Payroll Team |
| 3 | contains "salary" | Compensation | Payroll Team |
| 4 | Default | General | HR General Team |

---

## ✅ Outcome
- HR cases auto-categorized and routed instantly  
- HR teams receive only relevant requests  
- Demonstrates decision-driven workflow automation in ServiceNow  

---

## 📸 Screenshots / Artifacts
- `FlowDiagram.png` → Complete Flow
- `DecisionTableSetup.png` → Decision Table Rules
- `HRCaseResult.png` → Auto-Updated Case

---

## 👨‍💻 Author
**Srikanth Madabhushi**  
Generative AI & ServiceNow Learner | MS in AI | Building AI-Enabled ITSM & HRSD Solutions  
[LinkedIn Profile](https://www.linkedin.com/in/srikanthmadabhushi)

---

## 🧭 Future Enhancements
- Integrate with **Predictive Intelligence**
- Add **Sentiment Analysis** for free-text routing
- Include **Auto-Replies** using GenAI
