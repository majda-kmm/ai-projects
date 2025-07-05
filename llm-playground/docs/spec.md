# Interactive LLM Playground - Specifications

## Project Overview

This project is an interactive educational web app that helps users (students, educators...) explore and understand how large language models work. It combines hands-on experiments, live visualizations, and hyperparameter controls so users can see how tweaking inference changes outputs in real time.


## Main Features

### Core functionality

| Feature                   | Description                                 |
|----------------------------|--------------------------------------------|
| Prompt input               | Text box for entering custom prompts.      |
| Parameter sliders          | Adjust inference hyperparameters live.     |
| Multi-mode execution       | Different generation modes for exploration.|
| Real-time visualizations   | Display tokenization, logits, entropy etc. |

## User Controls (Hyperparameters)

| Parameter         | UI element | Range               | Explanation                          |
|-------------------|------------|---------------------|--------------------------------------|
| Temperature       | Slider     | 0.1 to 2.0           | Controls randomness by scaling logits|
| Top-k sampling    | Slider     | 1 to 100             | Keeps only top k probable tokens     |
| Top-p (nucleus)   | Slider     | 0.1 to 1.0           | Keeps smallest set with cumulative prob >= p |
| Max length        | Slider     | 10 to 500 tokens     | Limits generation length             |
| Dropout rate      | Slider     | 0 to 0.5             | Adds inference-time dropout          |
| MC samples        | Slider     | 1 to 20              | Runs multiple passes to show variance|

## Visualizations

| Visualization        | Description                                 |
|-----------------------|--------------------------------------------|
| Tokenization flow     | Shows how text is split into tokens.       |
| Logits bar chart      | Displays top N token probabilities.       |
| Entropy line graph    | Tracks uncertainty across tokens.         |
| MC samples overlay    | Shows variability across multiple runs.   |
| (Optional) Attention  | Maps input tokens to outputs visually.    |

## Modes

| Mode                    | What it does                            |
|--------------------------|---------------------------------------|
| Standard                 | Single generation with visualization. |
| Step-by-step             | Generates one token at a time.         |
| Dropout exploration      | Multiple runs on same prompt.          |
| Comparison mode          | Side-by-side comparison of settings.   |

## UI / UX Expectations

- Split screen layout:
  - Left pane: prompt input, sliders, mode selection, tooltips.
  - Right pane: generated output, token highlights, charts.
- Dark mode and light mode toggle.
- Smooth transitions and updates (animations).
- Tooltips that explain concepts like temperature or entropy.
- Clean, modern typography with ample spacing.

## Technical Stack

| Layer            | Technology choices                            |
|-------------------|----------------------------------------------|
| Frontend          | React + Next.js (or Vite), Tailwind CSS      |
| Animation         | Framer Motion                               |
| LLM backend       | Python (FastAPI or Flask) or Node (Express) with Hugging Face Transformers |
| Visualization     | Chart.js, Recharts or D3                    |
| Hosting           | Vercel / Netlify for frontend, lightweight API on Hugging Face Spaces or your own server |
| Data processing   | numpy, pandas for MC Dropout & entropy      |

## Possible Future Extensions

- Ability to save and load experiments.
- Export generated data to JSON/CSV.
- Small interactive quizzes (e.g. "Given these logits, which token is most probable?").
- Plug in multiple models (GPT-2, DistilGPT, LLaMA) for side-by-side comparison.

## Timeline (6 months)

| Weeks    | Goals                                                        |
|----------|--------------------------------------------------------------|
| 1-2      | Design wireframes (Figma / Canva) and finalize specs.        |
| 3-4      | Build frontend scaffold (Next.js / React), input & layout.   |
| 5-6      | Implement sliders, mode selector, state management.          |
| 7-8      | Integrate model inference backend, basic output display.     |
| 9-10     | Build tokenization & logits visualizations.                  |
| 11-12    | Add entropy plots and MC sampling overlays.                  |
| 13-14    | Polish animations, add tooltips, dark/light theme.           |
| 15-16    | Testing, small user demos, finalize docs.                    |
| 17-18    | Write a short technical report and portfolio summary.        |

## Repository Structure

├── /frontend       # React / Next.js app
├── /backend        # API for inference (FastAPI / Flask / Node)
├── /public_assets  # Logos, illustrations, diagrams
├── /notebooks      # For quick experiments on MC Dropout, entropy
├── /docs           # Markdown specs, architecture diagrams
├── package.json / requirements.txt
├── README.md / SPEC.md

## Deliverables

- Fully functional web app with adjustable LLM hyperparameters.
- Clear educational visualizations (tokenization, logits, entropy, MC variance).
- Clean repository with documented code, specifications and sample notebooks.
- A short report summarizing goals, methods, results and usage.