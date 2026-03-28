![](../../workflows/gds/badge.svg) ![](../../workflows/docs/badge.svg) ![](../../workflows/wokwi_test/badge.svg) ![](../../workflows/fpga/badge.svg)

# 2 Bit Full Adder 

A digital 2-bit full adder circuit designed for Tiny Tapeout. This project implements binary addition using basic logic gates, suitable for educational purposes and as a building block for larger arithmetic circuits.

- [View project documentation](docs/info.md)
- [View Wokwi project](https://wokwi.com/projects/your-wokwi-id) 

## 📋 Overview

This 2-bit full adder takes two 2-bit numbers and a carry-in, producing a 2-bit sum and a carry-out:
- **Inputs:** A1, A0, B1, B0, and Carry-in (Cin)
- **Outputs:** Sum1, Sum0 and Carry-out (Cout)

The circuit can be cascaded to create multi-bit adders for processors, calculators, and digital systems.

## 🔧 How It Works

The 2-bit full adder implements binary addition using two cascaded full adders:

### Logic Equations

For the first full adder:
- **Sum0** = A0 ⊕ B0 ⊕ Cin
- **Carry1** = (A0 & B0) | (A0 & Cin) | (B0 & Cin)

For the second full adder:
- **Sum1** = A1 ⊕ B1 ⊕ Carry1
- **Cout** = (A1 & B1) | (A1 & Carry1) | (B1 & Carry1)

### Truth Table

| A1 | A0 | B1 | B0 | Cin | Sum1 | Sum0 | Cout |
|----|----|----|----|-----|------|------|------|
| 0  | 0  | 0  | 0  | 0   | 0    | 0    | 0    |
| 0  | 0  | 0  | 0  | 1   | 0    | 1    | 0    |
| 0  | 0  | 0  | 1  | 0   | 0    | 1    | 0    |
| 0  | 0  | 0  | 1  | 1   | 1    | 0    | 0    |
| ... | ... | ... | ... | ... | ...  | ...  | ...  |
| 1  | 1  | 1  | 1  | 1   | 1    | 1    | 1    |

### Gate Implementation
- **4 XOR gates** - Generate the Sum outputs
- **4 AND gates** - Detect carry conditions
- **2 OR gates** - Combine carry outputs

## 🧪 How to Test

### Basic Testing
1. Apply inputs to A0, A1, B0, B1, and Cin using switches or push buttons
2. Observe Sum0, Sum1, and Cout on LEDs
3. Verify against the truth table above

### Simulation Testing
The GitHub action automatically runs tests on your design. Check the Actions tab for results.

### Hardware Testing
1. Connect power (3.3V-5V) to VCC and GND
2. Connect input switches to A0, A1, B0, B1, and Cin pins
3. Connect LEDs (with 220-330Ω resistors) to Sum0, Sum1, and Cout pins
4. Test all 32 input combinations

## 🔌 External Hardware Required

| Component | Quantity | Purpose |
|-----------|----------|---------|
| Push buttons or DIP switches | 5 | Inputs (A0, A1, B0, B1, Cin) |
| LEDs | 3 | Output indicators (Sum0, Sum1, Cout) |
| Resistors (220-330Ω) | 3 | Current limiting for LEDs |
| Breadboard | 1 | Prototyping |
| Jumper wires | ~15 | Connections |
| Power supply (3.3V-5V) | 1 | Circuit power |

## 📊 Implementation Stats

- **Cell count:** 110 logic cells
- **Utilization:** 1.88% of chip area
- **Wire length:** 886µm
- **Logic family:** Combinational (no clock required)

## 🚀 Tiny Tapeout Submission

This project is designed for Tiny Tapeout. The GitHub action automatically:
1. Fetches the netlist from Wokwi
2. Builds the ASIC files
3. Generates GDSII layout
4. Runs tests
5. Creates documentation

## 📁 Repository Structure
📦 your-repo-name/
│
├── 📂 .devcontainer/
│   └── devcontainer.json
│
├── 📂 .github/
│   └── 📂 workflows/
│       ├── gds.yaml
│       ├── docs.yaml
│       ├── wokwi_test.yaml
│       └── fpga.yaml
│
├── 📂 .vscode/
│   ├── settings.json
│   └── extensions.json
│
├── 📂 docs/
│   ├── 📂 images/
│   │   ├── circuit-diagram.png
│   │ 
│   │   └── wokwi-screenshot.png
│   ├── info.md
│   └── README.md
│
├── 📂 src/
│   ├── user_module.v
│   └── user_module_tb.v
│
├── 📂 test/
│   ├── 📂 data/
│   │   └── expected_outputs.txt
│   └── config.yaml
│
├── .gitignore
├── diagram.json
├── info.yaml
├── LICENSE
├── Makefile
└── README.md



## 🌐 Resources

- [Tiny Tapeout FAQ](https://tinytapeout.com/faq/)
- [Digital design lessons](https://tinytapeout.com/digital_design/)
- [Learn how semiconductors work](https://tinytapeout.com/siliwiz/)
- [Join the community on Discord](https://tinytapeout.com/discord)
- [Build your design locally](https://www.tinytapeout.com/guides/local-hardening/)

## 📈 Applications

- Building block for Arithmetic Logic Units (ALUs)
- Multi-bit adder circuits (cascade multiple 2-bit adders)
- Digital counters and accumulators
- Microprocessor design
- Educational tool for binary arithmetic


  | Platform | Link/Tag |
  |----------|----------|
  | LinkedIn | [#tinytapeout](https://www.linkedin.com/search/results/content/?keywords=%23tinytapeout) [@TinyTapeout](https://www.linkedin.com/company/100708654/) |
  | Mastodon | [#tinytapeout](https://chaos.social/tags/tinytapeout) [@matthewvenn](https://chaos.social/@matthewvenn) |
  | X (Twitter) | [#tinytapeout](https://twitter.com/hashtag/tinytapeout) [@tinytapeout](https://twitter.com/tinytapeout) |
  | Bluesky | [@tinytapeout.com](https://bsky.app/profile/tinytapeout.com) |

## 🙏 Acknowledgments

- Tiny Tapeout team for the educational shuttle
- Wokwi for the online simulator
- Open source EDA tools community

---

**Happy building!** 🎉
