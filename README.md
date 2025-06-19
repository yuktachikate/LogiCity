# LogiCity++: Neuro-Symbolic Traffic Reasoning

This project simulates urban traffic scenarios using symbolic agents and two different reasoning strategies:

- **LLM-based reasoning** (initially via GPT-4)
- **DeepProbLog-inspired symbolic reasoning** (FOL logic in Python)

It visualizes agent behavior (e.g., move or stop) across frames from a simulation.

---

## 🏗 Project Structure

- `Agent`: Represents cars, ambulances, etc. with attributes like age and position.
- `LogiCityEnv`: Simulates a simple city graph and agent movement.
- `symbolic_decision`: Encodes logical rules about how agents should act.
- `render_simulation_with_symbolic_logic`: Displays frame-wise simulation + reasoning results.

Image frames are loaded from:
```bash
~/Downloads/animation_simulation/  # with .tiff or .tif images
```

---

## ⚙️ Installation (VS Code / CLI)
```bash
python -m venv logicity_env
source logicity_env/bin/activate  # or .\logicity_env\Scripts\activate (Windows)
pip install networkx matplotlib python-dotenv pillow imageio
```

---

## 🚀 Run Simulation
```bash
python logicity_simulation.py  # or run cell-by-cell in Jupyter
```
It will render 50 image frames and overlay agent decisions like:
```
Agent 1: move
Agent 2: stop
... (per frame)
```

---

## 🤖 LLM-Based vs Symbolic (DeepProbLog-Style)

| Approach         | LLM (GPT-4)                             | Symbolic (DeepProbLog)                       |
|------------------|------------------------------------------|----------------------------------------------|
| Setup            | Prompt + GPT-4 via OpenAI API            | Logic rules in Python or ProbLog             |
| Flexibility      | Understands vague scenarios              | Requires structured symbolic input           |
| Cost/Latency     | High (API calls, non-deterministic)      | Fast, local, deterministic                   |
| Interpretability | Low                                      | High                                         |
| Use Case         | Natural language + perception tasks      | Reliable rule-based decision modeling        |

---

## ✅ Recommendation
- Use **LLMs** if you want to reason over natural scenes, user queries, or multimodal data.
- Use **symbolic systems (DeepProbLog)** if interpretability, determinism, and formal reasoning are required — especially in safety-critical settings like traffic.

For this project, symbolic logic performed reliably and is well-suited for small grid simulations.

---

## 🔮 Future Scope
- Integrate YOLO or CLIP to auto-convert frames to symbolic facts
- Extend symbolic logic to handle dynamic time and collisions
- Use DeepProbLog’s neural components for learned predicates
- Combine both: LLM to extract features, DeepProbLog to reason

---

Built with ❤️ using LogiCity concepts and Neuro-Symbolic AI tools.

![animation simulation GIF by Wolfram Research](https://github.com/user-attachments/assets/d1d16b8c-5fd3-46b9-9275-0fc5623b7d1d)


