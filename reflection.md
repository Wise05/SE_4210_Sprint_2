# Reflection of Building The Buffer Overflow Lab 

## What I Learned 
1. Conceptualizing Stack Architecture & Memory Layout

We examined how the C call stack operates in memory:

    Stack Organization: Visualizing how stack frames allocate memory, placing local variable buffers at lower addresses while saved control structures—like the Saved Frame Pointer (EBP/RBP) and Return Address (EIP/RIP)—reside at higher addresses.

    The Mechanism of an Overflow: How unbounded string functions (strcpy, gets) write memory upwards, allowing excessive input to spill out of designated buffer boundaries and overwrite critical control data.

2. Translating Complex Systems into Interactive Visualizations

To make an abstract security concept intuitive for students, we identified key visual and functional elements:

    Dual-View Design: Pairing a real-time C code execution panel with a live dynamic memory stack diagram so learners can connect line-by-line execution to state changes in memory.

    Color-Coded Memory Regions: Using distinct visual cues to demarcate safe buffer space, local variable regions, alignment padding, frame pointers, and sensitive return addresses.

    Interactive Control Controls: Utilizing input fields, sliders, step-by-step execution controls, and preset educational scenarios (Normal, Variable Overwrite, Return Address Hijack) to let users experiment at their own pace.

3. Emphasizing Defensive Engineering & Safety

    Pedagogical Safety First: We focused on building a safe web-based simulation rather than a functional exploit tool, keeping the environment contained entirely within browser JavaScript without generating real shellcode or executable payloads.

    Mitigation Awareness: Beyond showing how a stack smashes, we highlighted modern computer architecture defenses—such as Stack Canaries, ASLR, DEP/NX bits—and emphasized safe C programming practices (switching from strcpy to strncpy or fgets).

4. Structuring Open-Source & Classroom Resources

Finally, we put together comprehensive documentation (README.md) designed to help students, educators, and self-learners easily run, understand, and build upon the visualization tool.

## Workflow 

I asked gemini to build the website in thinking mode. It did well on its first try, so I kept that. I then asked it to write the README. 
