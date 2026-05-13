# EliteFit

**EliteFit** is a single-page web app that acts as a friendly fitness companion: calculate your BMI, share health goals or concerns, and get tailored exercise ideas—plus an on-page health assistant for common questions.

[**Live demo**](https://elitefittness.netlify.app/)

> **Disclaimer:** EliteFit is for general wellness and education only. It is **not** medical advice. Always talk to a qualified clinician before changing exercise or treatment, especially if you have a condition or injury.

---

## Features

- **BMI calculator** — Height, weight, and instant BMI category (underweight through obese) to guide the rest of the flow.
- **Health assessment** — Pick from common concerns (e.g. back pain, knee issues, weight loss, posture) or add your own; selections feed the recommendation engine.
- **Personalized exercise recommendations** — Rules combine BMI category and concerns with a structured exercise database (cardio, strength, yoga, rehabilitation, and more).
- **Exercise cards** — Clear presentation of suggested movements with difficulty and muscle targets.
- **Health chatbot** — Floating assistant with rule-based answers on fitness, nutrition, BMI, sleep, and related topics (no external API required).
- **Responsive UI** — Gradient layout, cards, and a chat widget that works on desktop and mobile.

---

## Tech stack

| Area        | Choice                          |
| ----------- | ------------------------------- |
| Framework   | [React 18](https://react.dev/)  |
| Language    | [TypeScript](https://www.typescriptlang.org/) |
| Build       | [Vite 5](https://vitejs.dev/)   |
| Styling     | [Tailwind CSS](https://tailwindcss.com/) |
| Icons       | [Lucide React](https://lucide.dev/) |
| State       | [Zustand](https://github.com/pmndrs/zustand) |

---

## Getting started

### Prerequisites

- **Node.js** 18+ (20+ recommended)
- **npm** 9+ (ships with Node)

### Install

```bash
git clone https://github.com/Vaishnavich217/EliteFit.git
cd EliteFit
npm install
```

### Development

```bash
npm run dev
```

Open the URL Vite prints (usually `http://localhost:5173`).

### Production build

```bash
npm run build
npm run preview   # optional local preview of the build
```

### Lint

```bash
npm run lint
```

---

## Project layout

```text
src/
├── App.tsx                 # Page shell and section flow
├── components/             # UI sections (BMI, assessment, recommendations, chatbot, etc.)
├── data/
│   └── exerciseDatabase.ts # Exercise catalog used for matching
├── store/
│   └── exerciseStore.ts    # Zustand store: profile, concerns, recommendations
├── types/
│   └── exercise.ts         # Shared TypeScript types
└── main.tsx                # App entry
```

---

## How it works (short)

1. User enters height and weight → BMI and category are stored.
2. After BMI exists, the health assessment appears; user selects concerns and submits.
3. The store merges **BMI rules** and **concern keywords** with `exerciseDatabase` to produce a deduplicated recommendation list.
4. The chatbot uses keyword matching to return canned, helpful replies—useful for demos and offline use.

---

## License

This project is private unless a license file is added. Contact the repository owner for reuse terms.
