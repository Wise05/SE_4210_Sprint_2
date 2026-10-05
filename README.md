# 🛡️ Interactive Stack Buffer Overflow Visualizer

An interactive, web-based educational tool designed to help students, cybersecurity enthusiasts, and computer science learners understand the mechanics of memory stack layouts and stack-based buffer overflows in a safe, visual environment.

> **Note**: This project is strictly an educational tool. It does **not** generate executable exploits, shellcode, or attack payloads. Its purpose is to visualize memory management concepts taught in introductory computer science and systems security courses.

---

## 🌟 Key Features

- **Interactive Stack Visualization**: Watch memory addresses fill byte-by-byte in real time as you type input into C-style string buffers.
- **Critical Memory Boundary Alerts**: Visual indicators show when user input exceeds the allocated buffer array and begins corrupting adjacent memory components:
  - Local variables
  - Compiler padding / Alignment space
  - Saved Frame Pointer (`EBP`/`RBP`)
  - **Return Address (`EIP`/`RIP`)**
- **Step-by-Step Execution Mode**: Step through vulnerable function execution line-by-line (`gets()`, `strcpy()`, string iteration) to observe how each instruction modifies stack memory.
- **Preset Educational Scenarios**:
  1. **Standard Function Call**: Normal, safe execution within buffer boundaries.
  2. **Variable Overwrite**: Overwriting a neighboring boolean variable (e.g., `isAdmin = 0` to `isAdmin = 1`) without crashing the return address.
  3. **Return Address Hijack**: Overwriting the return address to point to an arbitrary code target (e.g., `0xdeadbeef` or an unhandled exception handler).
- **Safe vs. Unsafe Code Comparison**: Side-by-side C code panel contrasting unsafe functions (`strcpy`, `gets`) with secure alternatives (`strncpy`, `fgets`, boundary checking).
- **Mitigation & Defense Explanations**: Educational summaries covering real-world defenses like Stack Cannaries (Cookies), ASLR (Address Space Layout Randomization), DEP/NX (Data Execution Prevention), and safe string functions.

---

## 🚀 Quick Start

Because the visualizer is built as a self-contained HTML/JS application, no server setup, build tools, or compilation steps are required.

### 1. Download / Clone
Clone or download this repository to your local machine:
```bash
git clone [https://github.com/your-username/buffer-overflow-visualizer.git](https://github.com/your-username/buffer-overflow-visualizer.git)
cd buffer-overflow-visualizer
