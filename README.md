# ⚛️ Quantum Entanglement Explorer

> An interactive, scientifically accurate quantum mechanics education platform built with Next.js 14 and TypeScript. Explore quantum entanglement, Bell states, CHSH inequality violations, and quantum noise — all powered by a real statevector simulator.

---

## 📸 Screenshots

> _Screenshots coming soon — run locally or deploy to Vercel to see the app in action._

---

## ✨ Features

The platform includes **7 interactive modules**:

| Module | Description |
|--------|-------------|
| 🏠 **Dashboard** | Overview of all modules with key quantum concepts |
| ⚛️ **Qubit Studio** | Visualize single-qubit states on the Bloch sphere, apply quantum gates |
| 🔗 **Entanglement Lab** | Create and explore all 4 Bell states via circuit simulation |
| 📊 **Measurement Lab** | Measure entangled qubits in X, Y, Z bases; see quantum correlations |
| ⚖️ **Comparison Lab** | Side-by-side: independent vs. entangled qubits — see the difference |
| 🔬 **Advanced Lab** | CHSH Bell inequality test, prove quantum mechanics beats classical bounds |
| 📚 **Learning Center** | Explanations, formulas, and the physics behind each module |

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| **Frontend** | Next.js 14 (App Router), React 18, TypeScript |
| **Styling** | Tailwind CSS, Framer Motion |
| **Charts** | Plotly.js, react-plotly.js |
| **Icons** | Lucide React |
| **Quantum Engine** | Custom TypeScript statevector simulator (`src/lib/quantumEngine.ts`) |
| **Python Backend** | NumPy-based statevector simulator (optional, for `/api/quantum/*`) |
| **Deployment** | Vercel (zero-config) |

---

## 📁 Project Structure

```
quantum-entanglement-explorer/
├── README.md
├── package.json
├── next.config.js
├── tsconfig.json
├── tailwind.config.ts
├── postcss.config.js
├── vercel.json
├── .gitignore
│
├── api/
│   └── quantum/
│       ├── _quantum_engine.py      # NumPy quantum simulator
│       └── requirements.txt
│
├── src/
│   ├── app/
│   │   ├── layout.tsx              # Root layout
│   │   ├── page.tsx                # Landing page → redirect to dashboard
│   │   ├── globals.css
│   │   ├── dashboard/
│   │   │   └── page.tsx
│   │   ├── qubit-studio/
│   │   │   └── page.tsx
│   │   ├── entanglement-lab/
│   │   │   └── page.tsx
│   │   ├── measurement-lab/
│   │   │   └── page.tsx
│   │   ├── comparison-lab/
│   │   │   └── page.tsx
│   │   ├── advanced-lab/
│   │   │   └── page.tsx
│   │   ├── learning-center/
│   │   │   └── page.tsx
│   │   └── api/
│   │       └── quantum/
│   │           ├── bell-state/route.ts
│   │           ├── measure/route.ts
│   │           ├── compare/route.ts
│   │           ├── chsh/route.ts
│   │           ├── noise/route.ts
│   │           └── qubit/route.ts
│   │
│   ├── components/
│   │   ├── quantum/
│   │   │   ├── BlochSphere.tsx
│   │   │   ├── BellStateVisualizer.tsx
│   │   │   ├── CircuitDiagram.tsx
│   │   │   ├── CorrelationMatrix.tsx
│   │   │   └── QuantumGatePanel.tsx
│   │   ├── charts/
│   │   │   ├── ProbabilityBar.tsx
│   │   │   └── CHSHGauge.tsx
│   │   └── ui/
│   │       ├── NavBar.tsx
│   │       └── ModuleCard.tsx
│   │
│   ├── lib/
│   │   └── quantumEngine.ts        # TypeScript quantum simulator
│   │
│   └── types/
│       └── quantum.ts
│
├── tests/
│   └── test_quantum_engine.ts
│
└── public/
    └── favicon.ico
```

---

## 🚀 Quick Start (Local Development)

### Prerequisites
- **Node.js** v18+ — [nodejs.org](https://nodejs.org)
- **npm** v9+ (bundled with Node.js)
- _(Optional)_ **Python** 3.11+ — [python.org](https://python.org)

### Run the App

```bash
# 1. Install Node.js from nodejs.org (v18+)
# 2. Install Python from python.org (3.11+)
# 3. Clone or extract project

cd quantum-entanglement-explorer
npm install
npm run dev
# Open http://localhost:3000
```

The app will be available at **http://localhost:3000**.

> **Note:** The TypeScript quantum engine (`src/lib/quantumEngine.ts`) works without Python. Python backend is optional and enables `/api/quantum/*` server-side endpoints.

---

## 🐍 Python Backend Setup (Optional)

The Python backend provides server-side quantum simulation via Next.js API routes. The TypeScript engine handles all client-side simulation and works standalone.

```bash
cd api/quantum
pip install -r requirements.txt
```

**requirements.txt** installs:
- `numpy` — statevector simulation
- `scipy` — advanced linear algebra (optional)

---

## ☁️ Vercel Deployment

Deploy in minutes with zero configuration:

```bash
# 1. Push to GitHub
git init
git add .
git commit -m "Initial commit: Quantum Entanglement Explorer"
git remote add origin https://github.com/YOUR_USERNAME/quantum-entanglement-explorer.git
git push -u origin main

# 2. Connect to Vercel (vercel.com)
# 3. Import repository from GitHub
# 4. Deploy (zero config needed — vercel.json handles everything)
```

Vercel will automatically:
- Detect Next.js framework
- Run `npm install` and `npm run build`
- Deploy to a global CDN

---

## 📦 Module Descriptions

### 1. 🏠 Dashboard
Entry point showing all available modules with descriptions, quick stats, and links. Gives a visual overview of the quantum concepts covered.

### 2. ⚛️ Qubit Studio
- Visualize a qubit state vector on the **Bloch sphere**
- Apply gates: **H, X, Y, Z, S, T** and see real-time state updates
- See probability amplitudes (α, β) and measurement probabilities
- Understand superposition through interactive experimentation

### 3. 🔗 Entanglement Lab
- Create all **4 Bell states**: Φ⁺, Φ⁻, Ψ⁺, Ψ⁻
- Watch the quantum circuit simulation step by step
- See how CNOT + Hadamard creates maximal entanglement
- Inspect the statevector components

### 4. 📊 Measurement Lab
- Measure entangled pairs in **X, Y, Z bases**
- Observe quantum correlations that cannot be explained classically
- Adjust shot count (100–10,000) for statistical exploration
- Visualize correlation matrices and probability distributions

### 5. ⚖️ Comparison Lab
- **Side-by-side comparison**: independent qubits vs. entangled pairs
- Independent qubits: correlation ≈ 0
- Entangled pairs: correlation > 0.9
- Bar charts and correlation values make the difference undeniable

### 6. 🔬 Advanced Lab (CHSH Test)
- Run the **CHSH Bell inequality** experiment
- Classical bound: |S| ≤ 2
- Quantum mechanics: S ≈ 2√2 ≈ 2.828
- Apply simulated **quantum noise** and see decoherence effects
- Demonstrates that quantum entanglement is real, not "hidden variables"

### 7. 📚 Learning Center
- Explanations of superposition, entanglement, measurement
- Mathematical formulas for Bell states and CHSH inequality
- Historical context (EPR paradox, Bell's theorem, Aspect's experiments)
- Glossary of quantum computing terms

---

## 🔧 Troubleshooting

| Problem | Solution |
|---------|----------|
| `npm install` fails | Ensure Node.js v18+ is installed: `node --version` |
| Port 3000 in use | Run `npm run dev -- -p 3001` to use port 3001 |
| Plotly charts not rendering | Try `npm install --legacy-peer-deps` |
| Python import errors | Run `pip install numpy` in the `api/quantum/` folder |
| Build fails on Vercel | Check `vercel.json` is present; ensure `next.config.js` has no syntax errors |
| TypeScript errors | Run `npx tsc --noEmit` to see type errors; ensure `tsconfig.json` is intact |

---

## 🔬 Scientific Accuracy Notes

This simulator is built for **education and accuracy**, not toy demos:

- **Statevector simulation**: All quantum states are represented as complex-valued probability amplitude vectors. No shortcuts.
- **Born rule**: Measurement probabilities are computed as |ψ|² from the statevector, not pseudo-random guessing.
- **CHSH violation**: The CHSH parameter S is computed from genuine quantum correlations. The quantum maximum of 2√2 ≈ 2.828 arises from Tsirelson's bound.
- **Bell states**: Created via proper Hadamard + CNOT circuit, matching textbook definitions exactly.
- **Noise model**: Depolarizing-like noise is applied to measurement counts, approximating real quantum hardware decoherence.
- **No Qiskit required**: The Python backend uses only NumPy for maximum portability on serverless platforms.

> **Reference**: Nielsen & Chuang, _Quantum Computation and Quantum Information_ (Cambridge, 2000)

---

## 📄 License

MIT License — free for educational and research use.

---

*Built with ❤️ for quantum computing education. Happy exploring the quantum world!*
