#  MSP430 Assembler, Linker & Loader

[![Python](https://img.shields.io/badge/Python-3.x-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![Tkinter](https://img.shields.io/badge/GUI-Tkinter-informational)](https://docs.python.org/3/library/tkinter.html)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

A systems programming project that implements an **assembler**, **linker**, and **loader** for the **MSP430** microcontroller architecture.
Written in Python, the system translates MSP430 assembly code into machine code, merges multiple ELF object files into a single executable, and simulates how the program is laid out in virtual memory.

##  Table of Contents

- [Project Structure](#-project-structure)
- [Components](#-components)
- [Reports](#-reports)
- [Tech Stack](#-tech-stack)
- [Getting Started](#-getting-started)
- [Authors](#-authors)
- [Notes](#-notes)

##  Project Structure

```
msp430-assembler-linker-loader/
├── generate_test_elfs/     → Automatic .elf file generator for testing
├── linked_output.elf       → Linker output (merged ELF file)
├── linker.py                → Linker module (ELF merging)
├── loader.py                → Loader module (memory placement, execution)
├── main.asm                 → Main assembly source file
├── main.elf                 → Main .elf object file
├── memory_map.png           → Memory map visualization
├── output.elf                → Assembler output (single ELF file)
├── report-1-assembler-design.pdf     → Assembler design report
├── report-2-compiler-architecture.pdf → Compiler architecture & GUI report
├── report-3-linker-loader-memory.pdf  → Linker, loader & virtual memory report
├── test4.py                  → Additional test file
├── utils.asm                 → Helper assembly module
└── utils.elf                 → .elf file generated from utils.asm
```

##  Components

### Assembler (Python + Tkinter GUI)
- Translates MSP430 assembly code into machine code using a two-pass compiler.
- Processes files like `main.asm` and produces object files in `.elf` format.
- The GUI allows writing code and inspecting the symbol table and generated machine code.

### Linker (`linker.py`)
- Takes multiple `.elf` files (e.g. `main.elf` and `utils.elf`) as input.
- Resolves symbols and performs relocation.
- Produces the final `linked_output.elf` file.

### Loader (`loader.py`)
- Places the ELF file into a virtual memory model (Flash, RAM, SFR, etc.).
- Performs relocation and segment placement.
- Determines real execution addresses to simulate running the program.

##  Reports

- `report-1-assembler-design.pdf` — Assembler design, opcodes, and addressing modes
- `report-2-compiler-architecture.pdf` — Compiler internals, GUI structure, assembly directives
- `report-3-linker-loader-memory.pdf` — Linker, loader, virtual memory structure, ELF processing

##  Tech Stack

- Python 3.x
- Tkinter (GUI)
- Custom assembler architecture
- ELF-like output format
- Virtual memory simulation
- Support for assembler directives such as `.macro`, `.equ`, `.ref`, `.global`

##  Getting Started

1. Make sure Python 3 is installed.

2. Launch the GUI:

```bash
python assembler_gui.py
```

3. Merge ELF files:

```bash
python linker.py
```

4. Load and run the ELF file in virtual memory:

```bash
python loader.py
```

##  Authors

This project was developed as a team effort by:

- **Adem Coşkun**
- **Emine Kayıt**
- **Sedanur Peker**
- **Zeliha Polat**

##  Notes

- This project was developed for educational purposes.
- It runs in a simulated virtual memory environment rather than on real MSP430 hardware.
- The symbol and literal tables are also displayed visually through the GUI.
