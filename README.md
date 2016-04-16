# wast-readmemh

Takes WebAssembly AST and produces bytecode in Verilog format.

The Verilog Hardware Description Language (HDL) provides a function `$readmemh()` to load a memory.

## Format

The syntax of the text file is described in the documentation of the IEEE standard for Verilog.
File contains two types of tokens: data and optional addresses.
The tokens are separated by whitespace and comments.
Comments may be single-line `//` or multi-line `/* */`, similar to C.
Addresses are specified by a leading `@` character and are always hexadecimal strings.
Data values are hexadecimal strings.
Data and addresses may contain underscore `_` characters.
The syntax supports 4-state logic for data values `(0, 1, x, z)`, where x represents an unknown value and z represents the high impedance value.

If no address is specified, the data is assumed to start at address 0.
Similarly, if data exists before the first specified address, then that data is assumed to start at address 0.

There are many corner cases which are not explicitly mentioned in the Verilog document.
