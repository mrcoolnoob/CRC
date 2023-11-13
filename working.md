## How to use CRC?

In the CRC augmentation method, you don't explicitly store the original CRC, but it's embedded in the data through the process. Here's a more detailed explanation:

1. **Calculate the CRC for the original data**: This gives you a CRC value.

2. **Augment the data**: You append zero bits to your data equal to the length of the CRC. This is your "augmented" data.

3. **Embed the CRC**: You then XOR the last bits of your augmented data (the appended zeros) with the CRC. This replaces the zero bits with the CRC value, effectively embedding the CRC into the data.

4. **Verification**: When you want to check the data, you calculate the CRC of the entire block of data (including the embedded CRC). If the data is intact, the result of this CRC calculation will be zero. This is because the CRC calculation will include the embedded CRC, cancelling it out.

So, you don't need to separately store or transmit the original CRC. It's embedded in the data itself through the augmentation process. If the data is corrupted, the CRC calculated at the receiving end will not be zero, indicating a data integrity issue.

## XOR in CRC

In C#, the XOR operation is performed using the `^` operator. Here's a simple example of how you can XOR two integers:

```csharp
int a = 5; // in binary: 101
int b = 3; // in binary: 011

// Perform XOR operation
int result = a ^ b; // result will be 6 (in binary: 110)
```

In this example, the binary representations of `a` and `b` are XORed together. The XOR operation compares each bit of `a` to the corresponding bit of `b`. If the bits are different, the result is 1; if the bits are the same, the result is 0. Hence, the result of `101 XOR 011` is `110`, which is 6 in decimal.

If you want to XOR more complex data types, such as byte arrays, you would need to iterate over the arrays and XOR the individual elements. Here's an example:

```csharp
byte[] array1 = new byte[] { 1, 2, 3, 4 };
byte[] array2 = new byte[] { 5, 6, 7, 8 };
byte[] result = new byte[array1.Length];

for (int i = 0; i < array1.Length; i++)
{
    result[i] = (byte)(array1[i] ^ array2[i]);
}
```

In this example, each byte in `array1` is XORed with the corresponding byte in `array2`, and the results are stored in `result`.
