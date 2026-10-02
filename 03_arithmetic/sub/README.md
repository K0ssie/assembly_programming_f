# SUB Operations and EFLAGS

## Program 1: sub1.asm

### Operation
50 - 80 = -30

### EFLAGS

- **CF: Set** - A borrow was required because 50 is smaller than 80.
- **PF: Set** - The low byte of the result has an even number of 1 bits.
- **AF: Set** - A borrow occurred from bit 4.
- **ZF: Cleared** - The result is not zero.
- **SF: Set** - The most significant bit of the 8-bit result is 1, representing a negative result.
- **OF: Cleared** - The signed result is within the valid 8-bit signed range.

### GDB Result

`eflags 0x287 [ CF PF SF IF ]`

Therefore, CF, PF, AF and SF are set, while ZF and OF are cleared.

---

## Program 2: sub2.asm

### Operation
1000 - 2000 = -1000

### EFLAGS

- **CF: Set** - A borrow was required because 1000 is smaller than 2000.
- **PF: Set** - The low byte of the result has an even number of 1 bits.
- **AF: Set** - A borrow occurred from bit 4.
- **ZF: Cleared** - The result is not zero.
- **SF: Set** - The most significant bit of the 16-bit result is 1.
- **OF: Cleared** - The result is within the valid signed 16-bit range.

### GDB Result

`eflags 0x287 [ CF PF SF IF ]`

Therefore, CF, PF, AF and SF are set, while ZF and OF are cleared.

