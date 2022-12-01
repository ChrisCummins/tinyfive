# TinyFive

<p align="center">
  <img src="https://github.com/OpenMachine-ai/tinyfive/blob/main/logo.jpg">
</p>

TinyFive is a simple RISC-V simulation model and
[ISS](https://en.wikipedia.org/wiki/Instruction_set_simulator) written entirely in Python.

You will love TinyFive if you want to learn how RISC-V works.
It's also useful for running neural networks on RISC-V: TinyFive lets you
simulate your RISC-V assembly code along with your neural network, all
in Python (and without relying on RISC-V toolchains). TinyFive is also useful
for ML scientists who are using ML/RL for compiler optimization (see
[CompilerGym](https://github.com/facebookresearch/CompilerGym/blob/development/README.md)).

### Running in colab notebook
You can run TinyFive in
[this colab notebook](https://colab.research.google.com/drive/1KXDPwSJmaOGefh5vAjrediwuiRf3wWa2?usp=sharing).
This is the quickest way to get started and should work on any machine.

### Running on your machine
Clone the repo and install packages `numpy` and `bitstring` as follows:
```
git clone https://github.com/OpenMachine-ai/tinyfive.git
cd tinyfive
pip3 install --upgrade pip
pip3 install numpy bitstring
```

To run the examples, type:
```
python3 examples.py
```

To run the test suite, type:
```
python3 tests.py
```

### Latest status
- TinyFive is still under construction, many things haven't been implemented and tested yet.
- 37 of the 40 base instructions `RV32I` and all 8 instructions of the M-extension `RV32M`
  are implemented, and many of them are tested. (The three missing instructions `fence`,
  `ebreak`, and `ecall` are really not applicable for TinyFive).
- Remaining work: improve testing, add extensions F and V, add RV64. See TODOs in
  the code for more details.

### Comparison
The table below compares TinyFive with other ISS projects.

| ISS | Author | Language | Mature? | Extensions | LOC |
| --- | ------ | -------- | ------- | ---------- | --- |
| [TinyFive](https://github.com/OpenMachine-ai/tinyfive)             | OpenMachine          | Python    | No               | I, M                | < 1k |
| [Pydgin](https://github.com/cornell-brg/pydgin)                    | Cornell University   | Python, C | Last update 2016 | A, D, F, I, M       | |
| [Spike](https://github.com/riscv-software-src/riscv-isa-sim)       | UC Berkeley          | C, C++    | Yes              | All                 | |
| [riscvOVPsim](https://github.com/riscv-ovpsim/imperas-riscv-tests) | Imperas              | C         | Yes              | All                 | |
| [Whisper](https://github.com/chipsalliance/SweRV-ISS)              | Western Digital      | C, C++    | Yes | A, B, C, D, F, I, M, S, U, V, Z* | |
| [Sail Model](https://github.com/riscv/sail-riscv)                  | Cambridge, Edinburgh | Sail, C   | Yes | All                              | |

### References
- [RISC-V spec](https://github.com/riscv/riscv-isa-manual/releases/download/Ratified-IMAFDQC/riscv-spec-20191213.pdf)
- Brief description of RISC-V instructions See [this RISC-V card](https://inst.eecs.berkeley.edu/~cs61c/fa18/img/riscvcard.pdf)
 for a brief description of most instructions
- Book "The RISC-V Reader: An Open Architecture Atlas" by David Patterson and Andrew Waterman
(2 of the 4 founders of RISC-V). Appendix A of this book defines all instructions.
The Spanish version of this book is
[available for free](http://riscvbook.com/spanish/guia-practica-de-risc-v-1.0.5.pdf),
other free versions are [available here](http://riscvbook.com).
- [Online simulator](https://ascslab.org/research/briscv/simulator/simulator.html) for debug

### Tiny Tech promise
Similar to [tinygrad](https://github.com/geohot/tinygrad),
[micrograd](https://github.com/karpathy/micrograd), and other “tiny tech” projects,
we believe that core technology should be simple and small (in terms of
[LOC](https://en.wikipedia.org/wiki/Source_lines_of_code)). Therefore, we will make sure
that the core of TinyFive (without tests and examples) will always be below 1000 lines.
Keep in mind that simplicity and size (in terms of number of instructions) is a key feature
of [RISC](https://en.wikipedia.org/wiki/Reduced_instruction_set_computer): the "R" in RISC
stands for "reduced" (as opposed to complex CISC).
