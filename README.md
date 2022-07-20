# LFSR
## Linear Feedback Shift Register Model in pure Python

```
    +-------+   +-------+     +-------+
+---|       |...|       |--+--|       |--+--
|   |  FFn  | | |  FF1  |  |  |  FF0  |  ^
|   |       | | |       |  |  |       |  |
|   +-------+ | +-------+  |  +-------+  |
|             |            |             |
|             v            v             |
|   +---------+------------+----------+  |
|   |                                 |  |
+-->|             f(x)                |--+
    |                                 |
    +---------------------------------+
```
Where f(x) is determined by the polynomial
provided to the LFSR.

Designed to test LFSR Mathematically for verification of Verilog Design.