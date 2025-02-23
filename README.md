## Gameboy Compiler

I've seen and used a lot of emulators for gameboy games and they're really cool. I, however, am a fan of running things natively. So this project is my attempt at writing a compiler from gameboy games to x86 (not using ARM because macOS has Rosetta and most windows computers are still x86).

### The Plan
This project is (clearly) WIP but here's the roadmap for myself and anyone else who reads:

- [ ] Setup a display, audio, and input API using SDL3 in C
  - [ ] Display API
  - [ ] Audio API
  - [ ] Input API
  - [ ] Combined interop file
- [ ] Parse(? not sure if I need to parse it technically) a rom file into its respective components (code and memory banks)
  - [ ] Read and understand the language spec
  - [ ] Make OCaml types which represents the langauge
  - [ ] Write a printer back into a ROM file for testing
  - [ ] Extract machine code from binary file into a value of the type
- [ ] Build and run an empty program that does nothing useful
  - [ ] Write empty "main" (probably won't be called main) function using LLVM
  - [ ] Write basic driver code which writes said empty LLVM file (for now)
  - [ ] Compile everything manually using clang
  - [ ] Convert manual commands into an OCaml program to make life easier
- [ ] Write a basic compiler from the Z80 machine language to LLVM (which will then be compiled using clang to x86 to make use of optimisations. Although I do have a basic compiler from LLVM to x86 written for a school project I could modify)
  - [ ] Write types for LLVM
  - [ ] Go instruction by instruction and compile it
  - [ ] yippee
- [ ] Try running with a simple demo gameboy program
- [ ] Add more complex language features
  - [ ] TBD (need to understand langauge spec first and see how gameboy ROMs actually use things) Examples would include things like cartridges which have a clock or multiple memory banks they switch between
- [ ] Build and run a proper game
  - [ ] I will not be writing a game (yet)
- [ ] (Maybe) Add optimisations
