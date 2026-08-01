# Hi, I'm Edward! 👋

I'm a Mathematics and Computer Science student at Duke University with interests in
iOS development, AI, and building software that transforms complex data into useful
products.

From May–August 2026, I was a Software Developer with Duke OIT, where I built an
AI-powered nutrition planning application using SwiftUI and Apple's Foundation Models
framework — see [mobile-ai](https://github.com/eykzhang/mobile-ai) for a writeup.

## Currently Working On

- 🧠 **[battle-engine](https://github.com/eykzhang/battle-engine)** — an ML/search
  battle engine for competitive Pokémon ("Stockfish for Pokémon"), and my hands-on
  path into machine learning: classical game-tree search → supervised learning on
  human replays → reinforcement learning via self-play. Phase 1 (classical search)
  gates are met: 84.8% win rate vs. a max-damage baseline, 59.2% vs. a scripted
  heuristic, over 500+ benchmarked battles each. Phase 2's ML pipeline (replay data →
  learned state encoding → trained win-probability model, wired into the same
  search) is built end-to-end and benchmarked. Phase 3 (PPO self-play RL) has its
  training pipeline built and independently reviewed twice — masked action sampling,
  warm-starting from the Phase 2 models, self-play against frozen past versions —
  with a real bug found and fixed via replay-based diagnosis along the way; strength
  verification against Phase 2 is next.
- 🎮 **[BattleBrain](https://github.com/eykzhang/battle-brain)** — a native iOS
  companion app for Pokémon Showdown that wraps the engine: team builder,
  competitive database, and engine-powered replay analysis, backed by serverless AWS

## Featured Projects

### 🧠 battle-engine + 🎮 BattleBrain — *a two-project system*

My flagship work: a Pokémon battle engine and the iOS app built around it, split the
way real game-analysis products are.

- **[battle-engine](https://github.com/eykzhang/battle-engine)** *(Python, C++
  planned)* — plays and analyzes Pokémon Showdown battles with game-tree search and
  machine learning. Pokémon is a genuinely hard AI problem — simultaneous moves,
  stochastic outcomes, and hidden information all at once — and the engine is built
  in staged phases, each gated on beating the previous version head-to-head over
  hundreds of measured battles. Phase 1's classical search bot (hand-crafted
  evaluation + expected-damage lookahead) beats scripted baselines 84.8% and 59.2%
  head-to-head; getting there included finding and fixing a root-cause evaluation
  bug via code review, verified by rerunning the full benchmark. Phase 2 built the ML
  side end-to-end — a replay data pipeline, a learned state encoding, and a trained
  win-probability model wired into the same search — with two further rounds of code
  review catching real correctness bugs before trusting the numbers. Phase 3 (PPO
  self-play reinforcement learning) is built and reviewed: reconciled two different
  action-space schemes between the RL library and the existing models, switched to
  masked action sampling after a review found illegal moves were silently
  misattributing training credit, and warm-started the policy from the Phase 2
  models by reshaping its network to match theirs exactly. Diagnosing a training
  plateau via replay inspection (the same technique used in Phases 1 and 2) surfaced
  a real bug: the policy exploiting a state-encoding blind spot to repeatedly
  re-attempt a move immediately after it had just failed. End-state mirrors
  Stockfish: train in Python, search in C++.
- **[BattleBrain](https://github.com/eykzhang/battle-brain)** *(Swift, SwiftUI,
  SwiftData, AWS)* — the product on top: full-depth team builder, competitive
  database, and turn-by-turn replay analysis with the engine's win-probability graph
  overlaid. On-device Foundation Models turn the engine's structured analysis into
  plain-language coaching — **ML plays, LLM explains** — with a serverless,
  infrastructure-as-code AWS backend (Lambda, API Gateway, DynamoDB, S3,
  EventBridge).

### 🍎 [Mobile AI](https://github.com/eykzhang/mobile-ai) *(Duke OIT, built May–Aug 2026)*
An on-device AI dining and nutrition assistant for Duke students — SwiftUI, SwiftData,
and an orchestrator + sub-agent pipeline over Apple's Foundation Models framework. Built
and functional, not yet released: launch is gated on Duke's dining-data provider
releasing a production client API (needed for live nutrition/allergen accuracy) and on
TestFlight testing. Repo is a portfolio writeup with a demo, since the source lives on
Duke's internal GitLab per university policy.

### ♠ [PokerNow Analyzer](https://github.com/eykzhang/pokernow-analyzer)
A Python application for parsing PokerNow hand histories into a SQLite database and
surfacing pot-odds/EV analysis to identify strategic decision-making leaks.

### 📈 [Entropy Trading Strategy](https://github.com/eykzhang/entropy-trading-strategy)
A backtested and verified trading strategy built on entropy-based signal recognition,
implemented in Python notebooks.

### 🌌 Cosmology Visualization
An interactive React application visualizing cosmological simulations from
undergraduate research.

## Tech

**Languages**

Swift • Python • Java • SQL • JavaScript • R • C++ *(learning)*

**Frameworks & Libraries**

SwiftUI • SwiftData • Foundation Models • PyTorch *(learning)* • React • pandas • Matplotlib

**Cloud & Tools**

AWS (Lambda, API Gateway, DynamoDB, S3) • Git • Docker • Xcode • VS Code

## Connect

- 💼 LinkedIn: https://linkedin.com/in/eykzhang
- 📫 Email: edward.zhang06@outlook.com
