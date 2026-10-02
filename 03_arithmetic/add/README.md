# ADD Operations and EFLAGS

## Program 1: add1.asm

### Operation
120 + 10 = 130

### Binary Result
120 = 01111000  
10  = 00001010  
130 = 10000010

### EFLAGS

- **CF: Cleared** - There was no carry out of the 8-bit result.
- **PF: Set** - The result `10000010` contains an even number of 1 bits.
- **AF: Set** - There was a carry from bit 3 to bit 4.
- **ZF: Cleared** - The result is not zero.
- **SF: Set** - The most significant bit is 1.
- **OF: Set** - 120 + 10 = 130, which is greater than the maximum signed 8-bit value of 127.

### GDB Result

`eflags 0xa96 [ PF AF SF IF OF ]`

Therefore, PF, AF, SF and OF are set, while CF and ZF are cleared.

---

## Program 2: add2.asm

### Operation
32000 + 500 = 32500

### EFLAGS

- **CF: Cleared** - There was no carry out of the 16-bit result.
- **PF: Cleared** - The low byte of the result does not contain an even number of 1 bits.
- **AF: Cleared** - There was no carry from bit 3 to bit 4.
- **ZF: Cleared** - The result is not zero.
- **SF: Cleared** - The most significant bit of the 16-bit result is 0.
- **OF: Cleared** - 32500 is within the signed 16-bit range.

### GDB Result

`eflags 0x202 [ IF ]`

The arithmetic flags are cleared. IF is set but is not an arithmetic result flag.
