# Modular Arithmetic and Bit Manipulation

{% hint style="warning" %}
This page is from my original notes and is not up to the latest quality standards. Read with care or [help make it better!](https://github.com/64bitpandas/cs61b-notes/pulls)
{% endhint %}

## Integer Types

| Type | Bits | Signed | Literals |
| :--- | :--- | :--- | :--- |
| byte | 8 | yes | 3, \(int\)17 |
| short | 16 | yes | None - must cast from int |
| char | 16 | no | 'a', '\n' |
| int | 32 | yes | 123, 0100 \(octal\), 0xff \(hex\) |
| long | 64 | yes | 123L, 0100L, 0xffL |

## Signed Numbers

* If a numerical type has N bits \(e.g. byte has N=8\), and is signed, then the number of values are 2^\(N-1\) and the last bit is used to determine the sign
* Range: -2^\(N-1\) to 2^\(N-1\) - 1
* Unsigned numbers have 0 to 2^N - 1 range

## Modular Arithmetic

* Definition: If a number x is out of range, yield the number equivalent to x % 2^n
* Mathematical definition: a = b\(mod n\) if a - b = kn for some integer k
* All arithmetic operations **wrap around** from overflow to the other side of the range
* Example: \(byte\)128 == \(byte\)\(127+1\) == \(byte\)\(-128\)
* **Bit representation:** Modular arithmetic in binary is equivalent to only keeping the last N bits of a result and removing the excess bits \(also works with negative numbers\)

## Type Conversion

* Java will automatically convert between types if **no information is lost** \(e.g. from byte to int\). 
* If converting the other direction \(from larger to smaller container\), an explicit cast is required \(e.g. `(char)int`\)
* Assignment statements are an exception to this: `aByte = 10` is fine even though 10 is an int literal
* Arithmetic operations \(+,  _...\) automatically \*promote_ operands \(e.g. `'A' + 2` is equivalent to `(int)'A' + 2`\)
  * Does not work if trying to add a larger value to a smaller type \(e.g. `aByte = aByte + 1` since operands become an int type which cannot be set equal to a byte type\)
  * But += works!

## Bit Operations

**Mask: &**

* `A & B` will only keep the bits that are 1 in A **AND** B
* Example: `00101100 & 10100111 == 00100100`

**Set: \|**

* `A | B` will keep the bits that are 1 in A **OR** B
* Example: `00101100 | 10100111 == 10101111`

**Flip: ^**

* `A ^ B` will keep the bits that are 1 in A **XOR** B
* In other words, 1 if bits are unequal in A and B, 0 otherwise
* Example: `00101100 ^ 10100111 == 10001011`

**Flip all: ~**

* `~A` will flip all the bits from 1 to 0 or 0 to 1 in A
* Example: `~10100111 == 01011000`

**Shift Left: &lt;&lt;**

* `A << n` will shift all bits left n places
* All newly introduced bits are 0
* Example: `10101101 << 3 == 01001000`
* `x << n` is equal to x \* 2^n

**Arithmetic Right: &gt;&gt;**

* `A >> n` will shift all bits **except for the signed bit** right n times
* Newly introduced bits are the same as the signed bit
* Example: `10101101 >> 3 == 11110101`

**Logical Right: &gt;&gt;&gt;**

* `A >>> n` will shift ALL bits right n times
* Newly introduced bits are 0
* Example: `10101101 >>> 3 == 00010101`
* Another example: `(-1) >>> 29 == 7` because it leaves 3 1-bits- ints are 32 bits

