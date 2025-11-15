# CPU in Logicism

This is a fully functional CPU :)

## A few more notes
- This CPU takes in three types of instructions: R, I, and J types with 16 bit instructions.
- It uses 8 general purpose registers `$r0`-`$r7`. Where `$r0` is hardwired to 0.
- It uses tri-state buffers + decoders for read ports (2 read ports + 1 write port in total).
- Rising edge clocked items: Register file, TTY
- Falling edge clocked items: PC register, data memory (memory latch), keyboard
  
## Instruction Set
- **Arithmetic / Logic**
  - `addi`, `add`, `sub`, `not`, `and`
- **Shifts**
  - `sll`, `srl` (logical shift right, no sign extension)
- **Memory**
  - `lw`, `sw` (word-addressed RAM)
- **Branches / Jumps**
  - `bgez`, `beq`, `j`, `jr`, `jal`
- **I/O**
  - `input`, `output`

## Repository Structure

```text
homework6/
├── cpu.circ             # Main CPU circuit
├── memory_latch.circ    # Provided memory latch subcircuit
├── hwtest.py            # Provided automated tester
├── tests/               # *.imem.lgsim / *.dmem.lgsim images for tests
├── programs/            # Assembly sources used in tests
├── asm-sim/             # Assembler and simulator
└── README.md            # This file
