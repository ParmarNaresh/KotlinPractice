# Kotlin tutorial with Example
## Basic types
#### Numbers
##### Integer types
- Byte:- Size 8 bits, Min value -128, Max value 127,
- Short:- Size 16 bits, Min value -32768, Max value 32767
- Int:- Size 32 bits, Min value -2,147,483,648, Max value 2,147,483,647
- Long:- Size 64 bits, Min value -9,223,372,036,854,775,808, Max value 9,223,372,036,854,775,807
```
val one = 1 // Int
val threeBillion = 3000000000 // Long
val oneLong = 1L // Long
val oneByte: Byte = 1
```

All variables initialized with integer values not exceeding the maximum value of Int have the inferred type Int.
If the initial value exceeds this value, then the type is Long
To specify the Long value explicitly, append the suffix L to the value.

##### Float types

- Float:- Size 32 bits, Significant 24 bits, Exponent 8 bits, Decimal digits 6-7
- Double:- Size 64 bits, Significant 53 bits, Exponent 11 bits, Decimal digits 15-16
-
```
val pi = 3.14 // Double
// val one: Double = 1 // Error: type mismatch
val oneDouble = 1.0 // Double
```
To explicitly specify the Float type for a value, add the suffix f or F. If such a value contains more than 6-7 decimal digits, it will be rounded.
```
val e = 2.7182818284 // Double
val eFloat = 2.7182818284f // Float, actual value is 2.7182817
```
For variables initialized with fractional numbers, the compiler infers the Double type.

To convert numeric values to different types, use Explicit conversions.
You can use underscores to make number constants more readable:
```
val oneMillion = 1_000_000
val creditCardNumber = 1234_5678_9012_3456L
val socialSecurityNumber = 999_99_9999L
val hexBytes = 0xFF_EC_DE_5E
val bytes = 0b11010010_01101001_10010100_10010010
```

All number types support conversions to other types:

- toByte(): Byte
- toShort(): Short
- toInt(): Int
- toLong(): Long
- toFloat(): Float
- toDouble(): Double
- toChar(): Char

Kotlin supports the standard set of arithmetical operations over numbers: +, -, *, /, %. They are declared as members of appropriate classes.

```
println(1 + 2)
println(2_500_000_000L - 1L)
println(3.14 * 2.71)
println(10.0 / 3)
```

Division between integers numbers always returns an integer number. Any fractional part is discarded.
```
val x = 5 / 2
//println(x == 2.5) // ERROR: Operator '==' cannot be applied to 'Int' and 'Double'
println(x == 2)
``` 

To return a floating-point type, explicitly convert one of the arguments to a floating-point type.
```
val x = 5 / 2.toDouble()
println(x == 2.5)
```

##### Bitwise operations
Kotlin provides a set of bitwise operations on integer numbers. They operate on the binary level directly with bits of the numbers' representation. Bitwise operations are represented by functions that can be called in infix form. They can be applied only to Int and Long.