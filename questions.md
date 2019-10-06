# Questions

## What's `stdint.h`?

* `stdint.h` is a header file in the standard `C` library that provides access to several functions related to integer standards, based on Microsoft's own BM-related data types.

## What's the point of using `uint8_t`, `uint32_t`, `int32_t`, and `uint16_t` in a program?

* They let us interpret parts of the binary code in a meaningful fashion, dependant on size and type.
* They are exact-width integer types that define

## How many bytes is a `BYTE`, a `DWORD`, a `LONG`, and a `WORD`, respectively?

* `BYTE` = **1 byte** (8-bit unsigned)
* `DWORD` = **4 bytes** (32-bits unsigned)
* `LONG` = **4 bytes** (32-bits signed)
* `WORD` = **2 bytes** (16-bits unsigned)

## What (in ASCII, decimal, or hexadecimal) must the first two bytes of any BMP file be? Leading bytes used to identify file formats (with high probability) are generally called "magic numbers."

* The first 2 bytes of any `BMP` file must be `BM`, which is `66` and `77` in **ASCII**, or 0x424d in **hexadecimal**.

## What's the difference between `bfSize` and `biSize`?

* The `bfSize` shows the **size, in bytes, of the bitmap file**, while `biSize` shows the **size, in bytes, of the BITMAPINFOHEADER**.

## What does it mean if `biHeight` is negative?

* If `biHeight` < 0 => the bitmap is a top-down DIB and its origin is the upper-left corner, which cannot be compressed.

## What field in `BITMAPINFOHEADER` specifies the BMP's color depth (i.e., bits per pixel)?

* The `biBitCount` defines the number of **bits per pixel** (i.e. the BMP's color depth). It determines the number of bits that define each pixel and the maximum number of colors in the bitmap.

## Why might `fopen` return `NULL` in `copy.c`?

* `fopen` is pointing to the infile with `read` permission. It might return `NULL` if there is no existent file.

## Why is the third argument to `fread` always `1` in our code?

* The 3rd argument in `fread` is always one to ensure that it's reading 1 pixel at a time.

## What value does `copy.c` assign to `padding` if `bi.biWidth` is `3`?

* If `bi.biWidth` = 3, then `int padding = (4 - (bi.biWidth * sizeof(RGBTRIPLE)) % 4) % 4;` means `padding = (4 - (3 * 3)) % 4) % 4 = (4 - 9 % 4) % 4 = (4 - 1) % 4 = 3 % 4 = 3`. That makes sure that in every line scanned the padding is equal to a pixel.

## What does `fseek` do?

* If there is any padding, `fseek` skips over it.

## What is `SEEK_CUR`?

* `SEEK_CUR` is an argument showing our current position within `fseek` function.
