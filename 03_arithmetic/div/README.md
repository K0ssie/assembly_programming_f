# DIV Operations and EFLAGS

## Program 1: div1.asm

### Operation

100 ÷ 7 = 14 remainder 2

* Dividend = 100
* Divisor = 7
* Quotient = 14
* Remainder = 2

### EFLAGS

GDB displayed:

`eflags 0x202 [ IF ]`

The `DIV` instruction does **not define the arithmetic flags** CF, PF, AF, ZF, SF, and OF. Therefore, these flags cannot be reliably described as set or cleared based on the division result.

* **CF:** Undefined
* **PF:** Undefined
* **AF:** Undefined
* **ZF:** Undefined
* **SF:** Undefined
* **OF:** Undefined
* **IF:** Set

The IF flag is unrelated to the result of the division.

---

## Program 2: div2.asm

### Operation

50000 ÷ 300 = 166 remainder 200

* Dividend = 50000
* Divisor = 300
* Quotient = 166
* Remainder = 200

### EFLAGS

GDB displayed:

`eflags 0x202 [ IF ]`

The `DIV` instruction does **not define** CF, PF, AF, ZF, SF, and OF. Therefore, these arithmetic flags cannot be reliably classified as set or cleared from this result.

* **CF:** Undefined
* **PF:** Undefined
* **AF:** Undefined
* **ZF:** Undefined
* **SF:** Undefined
* **OF:** Undefined
* **IF:** Set

The IF flag is unrelated to the division result.

### Conclusion

For both DIV programs, GDB displayed `0x202 [ IF ]`. The arithmetic flags should not be interpreted as set or cleared because the `DIV` instruction leaves them undefined.
