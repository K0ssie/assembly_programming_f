# MUL Operations and EFLAGS

## Program 1: mul1.asm

### Operation
25 × 10 = 250

### Result
The 8-bit multiplication produces 250, which fits within the 16-bit AX result.

### EFLAGS

- **CF: Cleared** - The upper half of the multiplication result is zero, so no significant overflow occurred.
- **OF: Cleared** - The upper half of the result is zero, so the result fits without overflow.
- **PF, AF, ZF, SF: Undefined** - The MUL instruction does not define these flags.

### GDB Result

`eflags 0x202 [ IF ]`

CF and OF are cleared. IF is unrelated to the multiplication result.

---

## Program 2: mul2.asm

### Operation
3000 × 200 = 600000

### Result
The multiplication produces 600000, which requires more than 16 bits. The result is stored in DX:AX.

### EFLAGS

- **CF: Set** - The upper half of the multiplication result in DX is non-zero.
- **OF: Set** - The multiplication result does not fit in the lower 16 bits alone.
- **PF, AF, ZF, SF: Undefined** - The MUL instruction does not define these flags.

### GDB Result

`eflags 0xa03 [ CF IF OF ]`

Therefore, CF and OF are set. IF is unrelated to the mu
ltiplication result.
