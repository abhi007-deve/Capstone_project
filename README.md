FinLoan AI 🚀
Institutional-Grade Loan Eligibility, Credit Analytics & Smart Financial Intelligence Platform
Overview
System Architecture
Key Features
1. AI Loan Eligibility Checker
2. Credit Score Analyzer & What-If Simulator
3. Smart EMI Calculator & Amortization Engine
4. AI Financial Tips & Strategic Advisory
5. Saved Reports & Audit History
6. Vertical Feature Navigation Menu
Mathematical Formulas & Banking Logic
API Documentation
Project Directory Structure
Getting Started
Prerequisites
Installation
Environment Setup
Running the Application
Available Scripts
Contributing
License
💡 Overview
FinLoan AI is a modern, full-stack financial technology web application designed to demystify borrowing, credit underwriting, and loan servicing.
Traditional loan approval systems often leave borrowers in the dark regarding their rejection reasons, debt capacities, or credit score impacts. FinLoan AI bridges this gap by combining institutional BFSI underwriting logic (FOIR, DTI caps, disposable income multipliers) with modern interactive financial simulators and AI-driven advisory.
Borrowers can evaluate their borrowing power, simulate credit score improvements, plan loan repayments with interactive amortization charts, and receive tailored roadmaps to qualify for prime interest rates.
🏛️ System Architecture
code
Text
+-----------------------------------------------------------------------------------+
|                                 CLIENT (BROWSER)                                  |
|                                                                                   |
|   +---------------------------------------------------------------------------+   |
|   |                       STICKY BRAND NAVBAR (Zone 1-3)                      |   |
|   +---------------------------------------------------------------------------+   |
|   |               VERTICAL FEATURE DROPDOWN & VIEW MODE SELECTOR              |   |
|   +---------------------------------------------------------------------------+   |
|                                       |                                           |
|       +-------------------------------+-------------------------------+           |
|       |                               |                               |           |
|       v                               v                               v           |
|  [Loan Checker]              [Credit Analyzer]                [EMI Calculator]    |
|  - DTI & FOIR Engine         - 300-900 Bureau Meter           - Reducing Balance  |
|  - Max Loan Estimator        - Utilization Simulator          - Amortization SVG  |
|  - Multi-Factor Risk Tiers   - Debt Payoff Simulator          - Schedule Exporter |
|                                       |                                           |
|       +-------------------------------+-------------------------------+           |
|       |                                                               |           |
|       v                                                               v           |
|  [AI Advisory & Tips]                                        [Saved Reports & PDF]|
|  - Debt Consolidation Strategy                               - Printable Dossier  |
|  - Cash-Flow Volatility Audit                                - Persistent History |
+-----------------------------------------------------------------------------------+
                                        |  REST API (/api/*)
                                        v
+-----------------------------------------------------------------------------------+
|                            FULL-STACK EXPRESS BACKEND                             |
|                                                                                   |
|   /api/health       -> System health & AI engine availability diagnostics         |
|   /api/analyze      -> Hybrid Underwriting: Rule Engine + Gemini / Claude LLM     |
|   /api/save         -> In-memory store + optional Google Sheets sync              |
|   /api/history      -> Audit trail retrieval and record comparison                |
+-----------------------------------------------------------------------------------+

🌟 Key Features

1. AI Loan Eligibility Checker
Institutional Risk Assessment: Evaluates borrower profile across gross salary, fixed commitments, existing loan EMIs, credit card debt, age, dependents, and employment tenure.
Dynamic Risk Categorization:
Highly Eligible (Score 80–100): Preferred interest rates, expedited approval.
Moderately Eligible (Score 60–79): Standard terms, minor debt restructuring recommended.
Low Eligibility (Score < 60): High FOIR/DTI alert, actionable turnaround plan provided.
Borrowing Capacity Estimator: Calculates the maximum safe loan amount without exceeding risk thresholds.

2. Credit Score Analyzer & What-If Simulator
Bureau Health Dial: Full 300–900 scale visual gauge with color-coded credit bands (Poor, Fair, Good, Very Good, Excellent).
Credit Card Utilization Slider: Models immediate credit score changes as credit card utilization drops below 30%.
Debt Payoff Simulator: Demonstrates credit rating improvements when paying off active revolving credit lines or personal loans.
One-Click Data Transfer: Apply your simulated score directly into the Loan Eligibility Checker.

3. Smart EMI Calculator & Amortization Engine
Reducing-Balance Live Engine: Exact monthly installments computed using standard compound banking formulas.
Principal vs. Interest Donut Chart: Dynamic SVG visual breakdown illustrating the true cost of debt.
Yearly Amortization Schedule: Full yearly ledger detailing starting balance, annual principal paid, annual interest, and remaining balance.
Loan Sync: Transfer amounts, rates, and tenures into the Loan Checker with a single click.

4. AI Financial Tips & Strategic Advisory
Cash-flow Volatility Analysis: Evaluates monthly burn rates and calculates optimal liquidity reserves (3–6 months).
Debt Consolidation Engine: Identifies high-APR unsecured credit and outlines refinancing potential.
Credit Enhancement Roadmap: Step-by-step timeline (Day 1, Month 1, Month 3, Month 6) for score optimization.

5. Saved Reports & Audit History
Printable Financial Appraisal: Comprehensive dossier formatted for export and printing (PDF ready).
Audit History: Stores previous evaluations for side-by-side scenario comparison.
Google Sheets Sync: Optional synchronization of evaluations directly into Google Spreadsheets via service account credentials.

6. Vertical Feature Navigation Menu
Space-Optimized Dropdown: Eliminates horizontal side-to-side scrolling tabs.
One-Down-One Vertical Stack: All 7 financial modules listed cleanly with color-coded badges, descriptions, and active status indicators.
Sequential Steppers: Previous (◀) and Next (▶) quick-navigation buttons.
Single View vs. Show All Modes: Toggle between an isolated focus view and a continuous multi-tool page.

📐 Mathematical Formulas & Banking Logic

1. Fixed Obligation to Income Ratio (FOIR)

Standard institutional safety benchmark: 
.
2. Debt-to-Income (DTI) Ratio

3. Equated Monthly Installment (EMI)
Calculated via standard reducing-balance amortized compound formula:

Where:
 = Monthly Installment (EMI)
 = Principal Loan Amount
 = Monthly Interest Rate (
)
 = Loan Tenure in Months
4. Maximum Eligible Loan Capacity

📡 API Documentation
GET /api/health
Checks the operational status of the backend, active AI provider (Gemini / Claude / Algorithmic Engine), and Google Sheets integration.
code
JSON
{
  "status": "healthy",
  "aiEngine": "gemini",
  "sheetsConnected": false,
  "timestamp": "2026-09-29T09:20:00.000Z"
}
POST /api/analyze
Submits applicant financial parameters to generate a full appraisal.
Payload:
code
JSON
{
  "age": 30,
  "monthlyIncome": 85000,
  "monthlyExpenses": 25000,
  "existingLoanEmi": 12000,
  "creditCardDebt": 20000,
  "creditScore": 750,
  "loanAmount": 1500000,
  "loanTenureMonths": 60,
  "loanType": "Home Loan",
  "employmentType": "Salaried",
  "employmentDurationYears": 4,
  "dependents": 1
}
GET /api/history
Returns previously completed evaluations from memory.
POST /api/save
Persists the generated appraisal report to persistent memory and Google Sheets (if configured).
📂 Project Directory Structure
code
Text
finloan-ai/
├── src/
│   ├── components/
│   │   ├── AiFinancialTips.tsx       # AI financial advisory & strategic roadmap
│   │   ├── CreditScoreAnalyzer.tsx   # Credit bureau score meter & what-if simulator
│   │   ├── DashboardOverview.tsx     # 4 primary metric cards with quick navigation
│   │   ├── EmiCalculator.tsx         # Reducing-balance EMI planner with amortization
│   │   ├── FinLoanLogo.tsx           # Brand SVG logo mark
│   │   ├── Footer.tsx                # Compliance footer & statutory notices
│   │   ├── HeroSection.tsx           # Hero intro & primary call-to-action
│   │   ├── HowItWorks.tsx            # Multi-step financial methodology guide
│   │   ├── LoanEligibilityChecker.tsx# Multi-factor loan qualification form & result
│   │   ├── Navbar.tsx                # Clean sticky top navigation bar
│   │   ├── RecentAnalyses.tsx        # Saved reports list & export
│   │   ├── ReportModal.tsx           # Printable PDF-style financial appraisal
│   │   └── TopTabBar.tsx             # Central vertical dropdown feature menu
│   ├── types/
│   │   └── finance.ts                # TypeScript interfaces & financial data models
│   ├── utils/
│   │   └── financialCalculations.ts  # EMI, FOIR, DTI, and credit scoring algorithms
│   ├── App.tsx                       # Main application orchestrator
│   ├── main.tsx                      # React root entry point
│   └── index.css                     # Tailwind CSS v4 styling & animations
├── server.ts                         # Express server with Vite middleware & AI proxy
├── package.json                      # Scripts & dependencies
├── tsconfig.json                     # TypeScript configuration
├── vite.config.ts                    # Vite build configuration
├── .env.example                      # Environment variables template
└── README.md                         # Project documentation
⚡ Getting Started
Prerequisites
Node.js (v18.0.0 or higher recommended)
npm (v9.0.0 or higher) or yarn / pnpm
Installation
Clone the repository:
code
Bash
git clone https://github.com/your-username/finloan-ai.git
cd finloan-ai
Install dependencies:
code
Bash
npm install
Environment Setup
Create your .env configuration from the provided example:
code
Bash
cp .env.example .env
Edit .env with your desired configuration:
code
Env
# AI Provider Configuration (Optional)
# If omitted, platform runs automatically in high-precision algorithmic Demo Mode
GEMINI_API_KEY="AIzaSy..."
ANTHROPIC_API_KEY="sk-ant-..."

# Google Sheets Sync (Optional)
GOOGLE_SERVICE_ACCOUNT_EMAIL="your-service-account@project.iam.gserviceaccount.com"
GOOGLE_PRIVATE_KEY="-----BEGIN PRIVATE KEY-----\n...\n-----END PRIVATE KEY-----\n"
GOOGLE_SHEET_ID="your_google_sheet_id_here"

# Server Configuration
PORT=3000
NODE_ENV="development"
Running the Application
Start the full-stack development environment:
code
Bash
npm run dev
Open http://localhost:3000 in your browser.
📜 Available Scripts
Command	Description
npm run dev	Starts Express server with Vite development middlewares on port 3000
npm run build	Compiles TypeScript and creates optimized production client build in /dist
npm run start	Launches the production Express server
npm run lint	Runs TypeScript type verification (tsc --noEmit)
npm run clean	Removes previous build artifacts
🛡️ Security & Privacy Notice
No Credential Leaks: API keys and service account credentials are kept strictly server-side.
Client-Side Data Safety: Form inputs are never shared with unauthorized external entities.
Algorithmic Fallback: The platform functions seamlessly offline or without third-party LLM keys using mathematical financial heuristics.
🤝 Contributing
Contributions are welcomed! Follow these steps:
Fork the Project.
Create your Feature Branch:
code
Bash
git checkout -b feature/NewFeature
Commit your Changes:
code
Bash
git commit -m 'feat: Add NewFeature'
Push to the Branch:
code
Bash
git push origin feature/NewFeature
Open a Pull Request.
📄 License
This project is licensed under the MIT License — see the LICENSE file for details.
