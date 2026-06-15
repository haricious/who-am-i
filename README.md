```
╔══════════════════════════════════════════════════════════════════════════════╗
║  SYSTEM IDENTIFIER  :  HARI                                                 ║
║  ENVIRONMENT        :  Anna University · ECE · SBM College · Dindigul       ║
║  OPERATIONAL MODE   :  ACTIVE — RTL Design Internship Pipeline               ║
║  PRIMARY TARGET     :  Mindgrove Technologies, Chennai                       ║
║  LONG-RANGE TARGET  :  Tier-1 Silicon · NVIDIA-class roles                  ║
║  BUILD STATUS       :  ████████████░░░░ 74% — First deployment: Aug 2026    ║
╚══════════════════════════════════════════════════════════════════════════════╝
```

---

## `$ cat /proc/hari/architecture`

```
Layer 0  ──  Electronics & Communication Engineering
Layer 1  ──  Embedded Systems · FPGA · SoC Interfaces
Layer 2  ──  Digital Design · RTL · Timing Closure
Layer 3  ──  Verilog · SystemVerilog · Simulation
Layer 4  ──  Verification · Testbench · Functional Coverage
          ──  [ domain boundary: software → silicon ]
```

The stack descends toward the substrate.  
Everything above is a means. Silicon is the objective.

---

## `$ status --active`

```
┌─────────────────────────────────────────────────────────────┐
│  ACTIVE PIPELINE                               [June 2026]  │
├────────────────────────────┬──────────┬────────────────────-┤
│  Deliverable               │  Status  │  Target             │
├────────────────────────────┼──────────┼─────────────────────┤
│  4-bit ALU                 │  ██████  │  Complete           │
│  UART Transmitter          │  ████░░  │  In progress        │
│  Synchronous FIFO          │  ███░░░  │  In progress        │
│  RISC-V RV32I ALU + RF     │  ██░░░░  │  Scheduled          │
│  Verilog HDL (Udemy)       │  █████░  │  Near complete      │
│  Portfolio site            │  ██████  │  Live               │
└────────────────────────────┴──────────┴─────────────────────┘
```

---

## `$ ls -lh ./projects`

**[`fpga-battery-soc-soh`]**  
Reconfigurable FPGA architecture for real-time multi-chemistry battery SoC + SoH estimation using Extended Kalman Filter. Targets Xilinx FPGAs. Journal submission in progress (Elsevier · Microprocessors and Microsystems).

**[`4bit-alu-rtl`]**  
Synthesizable 4-bit ALU in Verilog. Full testbench. Gate-level simulation.

**[`uart-tx`]**  
UART transmitter module. Parameterised baud, start/stop logic, shift register implementation.

**[`sync-fifo`]**  
Synchronous FIFO with full/empty flag logic, parameterised depth and width.

**[`riscv-rv32i-alu-rf`]**  
ALU and register file for a pipelined RV32I core. In development.

---

## `$ grep -r "domain" /proc/hari/capabilities`

```
RTL Design         ──  Verilog · SystemVerilog · FSM · Datapath
Digital Design     ──  Combinational · Sequential · Clocking · Reset
Verification       ──  Directed testbench · Waveform analysis · Assertion basics
FPGA               ──  Vivado · Synthesis · Implementation · Bitstream
SoC Concepts       ──  AXI4 · APB · Bus protocols · Memory-mapped IO
Simulation         ──  ModelSim · iVerilog · GTKWave
Hardware Theory    ──  Timing analysis · Setup/hold · Clock domains
Software (legacy)  ──  C · Python · Embedded C · Git
```

---

## `$ trace --evolution`

```
t = 0       Embedded systems · MATLAB · signal processing
            │
t = +1      FPGA prototyping · HDL fundamentals
            │
t = +2      RTL Design · Verilog · digital architecture
            │
t = +3      Verification · SoC interfaces · timing
            │
t = NOW ──► Silicon target acquired
```

The trajectory is not lateral. It is downward — toward the gate.

---

## `$ cat /etc/hari/objective`

```
NEAR-TERM   Internship — RTL Design — July/August 2026
            Target: Mindgrove Technologies, Chennai

MID-TERM    Silicon design role — Verilog/SV · Verification · STA
            Environment: Startup · fabless · tape-out exposure

LONG-TERM   Senior RTL / Digital Design Engineer
            Domain: ASIC · SoC · sub-7nm design
            Reference class: NVIDIA · Qualcomm · TSMC ecosystem
```

---

## `$ read /proc/hari/research`

**Domain:** FPGA-based real-time estimation systems  
**Method:** Extended Kalman Filter on reconfigurable hardware  
**Application:** Multi-chemistry Li-ion battery SoC/SoH joint estimation  
**Contribution:** Resource-efficient fixed-point EKF architecture on Artix-7  
**Status:** Paper authored · Journal review pipeline

---

## `$ inspect --philosophy`

```
Correctness before speed.
Simulation before synthesis.
Read the datasheet before the tutorial.
A passing testbench is not a working design.
Understand the timing path before fixing the warning.
```

Hardware does not tolerate ambiguity.  
That constraint is what makes it worth doing.

---

## `$ uptime --system`

```
Institution   Anna University affiliated · B.E. ECE · 2022–2026
Location      Tamil Nadu, India
Languages     Tamil (native) · English (technical)
Status        Final year · Internship-ready
```

---

## `$ ping haricious-in.vercel.app`

```
Portfolio ──── haricious-in.vercel.app          [LIVE]
Research  ──── FPGA Battery Management Paper    [IN REVIEW]
Pipeline  ──── RTL Project Portfolio            [BUILDING]
```

---

<sub>
System documentation. Not a résumé. Not a personal statement.  
The work speaks in waveforms.
</sub>
