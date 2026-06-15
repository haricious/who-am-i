```
╔══════════════════════════════════════════════════════════════════════════════╗
║  HARI SANKAR SARAVANAN                                                       ║
║  ECE · B.E. 2023–2027 · SBM College of Engineering and Technology            ║
║  Dindigul, Tamil Nadu, India                                                 ║
║  Direction: VLSI · Digital Design · RTL · Chip Design                        ║
╚══════════════════════════════════════════════════════════════════════════════╝
```

---

## WHERE I ACTUALLY AM

Most of my peers moved toward software. I went the other way, down the stack,
past the operating system, past the firmware, past the drivers, into the logic
that has nowhere to hide behind a framework.

That's the direction. The honest read is that the technical work is early-stage.
The exercises are real. The projects aren't there yet. This document tracks both.

---

## DOMAIN STATUS

*Bars replaced with honest levels. The gap column is what matters most.*

```
 ┌────────────────────────────────────────────────────────────────────────────┐
 │                                                                            │
 │  AREA                   LEVEL          WHAT'S THERE    WHAT'S MISSING      │
 │  ─────────────────────────────────────────────────────────────────────     │
 │  Verilog / RTL          Beginner+      FSMs, MUX,      SystemVerilog,      │
 │                                        mem models,     SVA, STA, CDCs,     │
 │                                        HDLBits track   reset strategy      │
 │                                                                            │
 │  FPGA Tools             Beginner       Vivado/Quartus  Constraint files    │
 │                                        synthesis,      (XDC/SDC),          │
 │                                        P&R, IP Integ.  timing closure      │
 │                                                                            │
 │  Digital Design Theory  Beginner       Gate-level,     Pipelining,         │
 │                                        K-maps, basic   hazards,            │
 │                                        sequential      architecture depth  │
 │                                                                            │
 │  Embedded (STM32/C)     Learning       Register-level  Nothing shipped.    │
 │                                        C, peripheral   No deliverable yet  │
 │                                        setup                               │
 │                                                                            │
 │  MATLAB / Simulink      Functional     EKF, battery    Not a core          │
 │                                        ECM, Simscape   direction           │
 │                                                                            │
 │  Computer Architecture  Exploring      P&H in progress Pipeline impl,      │
 │                                                        RISC-V datapath,    │
 │                                                        ALU in Verilog      │
 │                                                                            │
 │  Verification           NOT STARTED    —               SVA, constrained    │
 │  [CRITICAL GAP]                                        random, formal      │
 │                                                        tools, UVM basics   │
 │                                                                            │
 │  ASIC / Physical Design NOT STARTED    —               OpenLane, Sky130,   │
 │  [REQUIRED FOR GOAL]                                   std cell flow,      │
 │                                                        ASIC vs FPGA diff   │ 
 │                                                                            │
 └────────────────────────────────────────────────────────────────────────────┘
```

---

## COMPLETED WORK

### `[2026.01]` — Joint SoC & SoH Estimation for Battery Management Systems
**Gandhigram Rural Institute · Research Internship**
*Category: Signal Processing / Estimation — this is not an RTL project.*

Built a combined State-of-Charge and State-of-Health estimation system for
a 12V, 7Ah lead-acid battery using MATLAB, Simulink, Simscape Electrical,
and an Extended Kalman Filter.

```
ARCHITECTURE:
  Battery Pack Model (Simscape)
    └── First-order RC Equivalent Circuit
          ├── OCV–SoC Lookup Table
          ├── Coulomb Counting (with drift correction)
          ├── Temperature Compensation
          └── Extended Kalman Filter
                ├── SoC Estimation
                └── SoH Tracking (capacity fade + resistance growth)

WHAT BROKE:
  Covariance matrix tuning. Small parameter errors caused EKF predictions
  to diverge from the battery model. The algorithm was correct.
  The model assumptions were wrong.

WHAT IT TAUGHT:
  Estimation accuracy depends as much on model quality as on the algorithm.
  The EKF doesn't know your battery is wrong. It trusts your equations.

WHAT THIS PROJECT IS NOT:
  Hardware. No RTL. No FPGA. No synthesis report. No constraint file.
  This is simulation work and should be read as such.
  It belongs here because the research environment was real
  and the estimation problem was not trivial.
  It does not demonstrate digital design capability.
  A VLSI interviewer should weigh it accordingly.
```

---

## RTL PRACTICE LOG

*These are exercises. Not projects. The distinction matters.*

A public record of HDLBits modules, FPGA tool workflows, and Verilog exercises.
Every entry logs what synthesized, what didn't, and why.

| Entry | Module | Status | Key Lesson |
|---|---|---|---|
| Part 09 | 8×1 MUX from 4×1 blocks (IP Integrator) | ✓ | Verification takes longer than building. This was still an exercise, not a design. |
| Part 10 | BRAM · Distributed RAM · ROM · COE | ✓ | Build from scratch first. Then the IP block makes sense. |
| Part 10 | ROM-based half-wave rectifier | ✓ | Misread the spec as RAM. Both kept. Wrong assumption ≠ wrong logic. |
| Active | HDLBits track Section 15+ | → | Practice track. Not a milestone. Foundation, not capability. |

**What this log is:**
Tool familiarity. Syntax familiarity. The gap between this and a real RTL project
is significant. A UART controller, a synchronous FIFO, a simple pipeline —
those are the next level. None of those are here yet.

**Repository:** [`mark-1-rtl-learning-verilog-hdl`](https://github.com/haricious/mark-1-rtl-learning-verilog-hdl)

---

## GAP REGISTER

*Borrowed from hardware: a register is a record of current state.
This is an honest record of what's missing.*

```
 ┌─────────────────────────────────────────────────────────────────────────┐
 │                                                                         │
 │  SYSTEMVERILOG          Not started.                                    │
 │                         Industry standard for RTL design and            │
 │                         verification. Interfaces, structs, packages,    │
 │                         assertions. "Verilog only" will be noticed      │
 │                         in technical screens at serious companies.      │
 │                                                                         │
 │  VERIFICATION           Not started.                                    │
 │                         No SVA. No constrained-random testbench.        │
 │                         No formal tools. Verification is half the job   │
 │                         in digital design. Right now it's a philosophy  │
 │                         cited in the build log, not a skill.            │
 │                                                                         │
 │  STATIC TIMING ANALYSIS Not studied.                                    │
 │                         Setup/hold time, timing paths, XDC/SDC          │
 │                         constraint files, critical path analysis.       │
 │                         Writing Verilog without STA knowledge means     │
 │                         synthesis failures have no framework to debug.  │
 │                                                                         │
 │  CLOCK DOMAIN CROSSING  Not studied.                                    │
 │                         Critical for any real multi-clock design.       │
 │                         Synchronizers, FIFO-based CDCs, metastability.  │
 │                                                                         │
 │  ASIC DESIGN FLOW       Not started.                                    │
 │                         OpenLane, Sky130, standard cells, timing libs,  │
 │                         ASIC vs FPGA design differences. The goal says  │
 │                         "chip design." This gap is a contradiction.     │
 │                                                                         │
 │  REAL RTL PROJECT       Does not exist yet.                             │
 │                         The log has exercises. Nothing substantial      │
 │                         enough to demonstrate design capability to a    │
 │                         hiring team. This is the most critical gap.     │
 │                         Everything else in this document builds toward  │
 │                         closing this one.                               │
 │                                                                         │
 └─────────────────────────────────────────────────────────────────────────┘
```

---

## NEXT BUILD

*One real project. Not another exercise. This is the current priority.*

**Target:** UART Controller — Full-duplex, Tx + Rx, synthesized to Basys3

```
WHY THIS:
  Forces proper FSM design with real timing requirements.
  Requires a testbench that verifies behavior — not just runs.
  Has a constraint file (XDC) and a synthesis timing report.
  Produces output that works on real hardware.
  Bridgeable to embedded: write a bare-metal C driver for the same
  peripheral. RTL and embedded meet at one design.

SUCCESS CRITERIA (before this is "done"):
  [ ] Baud rate generator correct at multiple frequencies
  [ ] FSM correct on edge cases — start bit, stop bit, idle, framing error
  [ ] Timing closure at target frequency with constraint file
  [ ] Assertions on protocol behavior (first SVA attempt)
  [ ] Testbench with directed and at least some randomized tests
  [ ] Synthesis report in GitHub with max frequency documented
  [ ] Failure log with root cause analysis

WHAT COMES AFTER:
  Synchronous FIFO with proper handshaking.
  Or a simple pipelined CPU datapath — even partial.
  Something that forces STA and CDCs into the picture.
```



## BACKGROUND BEFORE ENGINEERING

```
2017–2018   Salesperson · Senthil Stores
            → Consistency as a discipline. Showing up is its own skill.

2019        Salesperson · Family Mart
            → Smooth operations come from small processes working correctly.

2021        Customer Service · Sai Netpark (Govt. Document Services)
            → Accuracy is a form of engineering. A small typo becomes
              someone else's problem.

2023        Packaging Associate · Malleswar Handlooms
            → Supply chains are systems. Workflow optimization
              exists everywhere — not just in code.
```

None of these were dead time. Every one of them taught a systems principle
that showed up later in a circuit. But they are context — they are not
a substitute for technical depth, and they're not presented as one.

---

## TOOLCHAIN

```
HDL           ::  Verilog
                  [SystemVerilog — not started. This is the next language.]
FPGA TOOLS    ::  Xilinx Vivado · Intel Quartus
SIMULATION    ::  ModelSim · GTKWave · Simulink
MATH/SIM      ::  MATLAB · Simscape Electrical
EMBEDDED      ::  C · STM32 [in progress — no deliverable yet]
HARDWARE      ::  KiCad [early stage]
VERSION CTRL  ::  Git · GitHub
DOCUMENTATION ::  haricious.in
```

---

## TRAJECTORY

```
2017  ──  First job. Learn to show up.
2021  ──  Document services. Learn that accuracy is a form of engineering.
2023  ──  ECE begins. Curiosity gets a direction.
2024  ──  Digital electronics. Gate-level layer starts making sense.
2025  ──  C, MATLAB. Tooling takes shape.
2026  ──  BMS internship at Gandhigram. First real research environment.
          (Simulation work — valuable, not RTL.)
          RTL practice log begins. Exercises, not projects. Gaps mapped.
          ── NOW: UART controller build. First real RTL project. ──
          Target: VLSI internship. Chennai or Bengaluru.
          To close: SystemVerilog. STA. One real project.
2027  ──  B.E. complete. Entry-level digital design or verification role.
  ▼
  ∞   ──  Chip design. The layer where code becomes physics.
          The gap between here and there is real.
          The path is clear. Going anyway.
```

---

## WHERE THIS IS DOCUMENTED

**[haricious.in](https://haricious-in.vercel.app)** — Full archive.

```
BUILD LOG          Projects from idea to outcome, failures included.
FIELD NOTES        Short lessons. Uncomfortable realizations.
FAILURE ARCHIVE    Broken designs and root causes.
```

---

## CONTACT

```
EMAIL     iamhari1812@gmail.com
LINKEDIN  linkedin.com/in/haricious
SITE      haricious-in.vercel.app
GITHUB    github.com/haricious
```

---

```
──────────────────────────────────────────────────────────────────────────────
  NOTE :: This profile is a live document, not a summary of achievements.
          The work is in progress. The gaps are documented alongside it.
          The point is to make the process visible — including where
          the process hasn't produced enough yet.
──────────────────────────────────────────────────────────────────────────────
```
