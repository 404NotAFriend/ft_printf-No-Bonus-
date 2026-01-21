<div align="center">

<!-- Animated Header -->
<img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/Printer.png" width="80"/>

# 🖨️ ft_printf - Recreating printf()

<img src="https://img.shields.io/badge/Score-100%2F125-success?style=for-the-badge&logo=42&logoColor=white"/>
<img src="https://img.shields.io/badge/Circle-1-00BABC?style=for-the-badge&logo=42&logoColor=white"/>
<img src="https://img.shields.io/badge/Language-C-00599C?style=for-the-badge&logo=c&logoColor=white"/>
<img src="https://img.shields.io/badge/Norminette-passing-success?style=for-the-badge&logo=42&logoColor=white"/>

**Because ft_putnbr() and ft_putstr() aren't enough - Master variadic functions by reimplementing printf()**

<img src="https://user-images.githubusercontent.com/74038190/212284100-561aa473-3905-4a80-b561-0d28506553ee.gif" width="600"/>

</div>

---

## <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/Light%20Bulb.png" width="25"/> About The Project

**ft_printf** is one of the first major challenges in the 42 curriculum where you'll implement your own version of the legendary `printf()` function. This project introduces you to the world of **variadic functions** - functions that can accept a variable number of arguments.

You'll learn how to parse format specifiers, handle different data types, and manage conversions - all while maintaining perfect memory management and following The Norm. This is where you truly start to understand the magic behind C's most versatile output function!

---

## <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Travel%20and%20places/Rocket.png" width="25"/> Implemented Conversions

<table>
<tr>
<td width="50%">

### 📝 Character & String
- ✅ `%c` - Single character
- ✅ `%s` - String
- ✅ `%%` - Literal percent sign

### 🔢 Numbers
- ✅ `%d` - Signed decimal integer
- ✅ `%i` - Signed integer (same as %d)
- ✅ `%u` - Unsigned decimal integer

</td>
<td width="50%">

### 🔤 Hexadecimal & Pointers
- ✅ `%x` - Hexadecimal (lowercase)
- ✅ `%X` - Hexadecimal (uppercase)
- ✅ `%p` - Pointer address

### 🎯 Features
- ✅ No buffer management
- ✅ Returns printed character count
- ✅ Handles all edge cases

</td>
</tr>
</table>

---

## <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/Gear.png" width="25"/> Technical Stack

![C](https://img.shields.io/badge/C-00599C?style=for-the-badge&logo=c&logoColor=white)
![Make](https://img.shields.io/badge/Make-427819?style=for-the-badge&logo=cmake&logoColor=white)
![GCC](https://img.shields.io/badge/GCC-00599C?style=for-the-badge&logo=gnu&logoColor=white)
![Valgrind](https://img.shields.io/badge/Valgrind-3B4D50?style=for-the-badge&logo=gnu&logoColor=white)
![Norminette](https://img.shields.io/badge/Norminette-42-00BABC?style=for-the-badge)

---

## <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/File%20Folder.png" width="25"/> Project Structure

```
ft_printf/
├── Makefile                 # Build automation
├── ft_printf.h              # Header file with prototypes
├── ft_printf.c              # Main printf implementation
├── ft_printf_utils.c        # Conversion utilities
├── ft_printf_hex.c          # Hexadecimal conversions
├── ft_printf_num.c          # Number conversions
└── README.md                # This file
```

---

## <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/Hammer%20and%20Wrench.png" width="25"/> Installation & Usage

### Prerequisites
- GCC compiler
- Make

### Compilation

```bash
# Clone the repository
git clone https://github.com/404NotAFriend/ft_printf.git
cd ft_printf

# Compile the library
make

# Clean object files
make clean

# Full cleanup (includes libftprintf.a)
make fclean

# Recompile everything
make re
```

### Using ft_printf in Your Project

```c
#include "ft_printf.h"

int main(void)
{
    int count;
    
    // Basic usage
    ft_printf("Hello, %s!\n", "42");
    
    // Multiple conversions
    ft_printf("Number: %d, Hex: %x\n", 42, 42);
    
    // Return value (number of characters printed)
    count = ft_printf("Count me: %c%c%c\n", 'a', 'b', 'c');
    ft_printf("Printed %d characters\n", count);
    
    // Pointer address
    int x = 42;
    ft_printf("Address: %p\n", &x);
    
    return (0);
}
```

```bash
# Compile with ft_printf
gcc main.c -L. -lftprintf -I.
```

---

## <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/Briefcase.png" width="25"/> Function Overview

### Main Function

```c
int ft_printf(const char *format, ...);
```

**Parameters:**
- `format`: Format string with conversion specifiers
- `...`: Variable number of arguments

**Return value:**
- Number of characters printed
- -1 on error

---

## <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/Magnifying%20Glass%20Tilted%20Left.png" width="25"/> Conversion Examples

```c
// Character and String
ft_printf("Char: %c\n", 'A');                    // Output: Char: A
ft_printf("String: %s\n", "42 School");          // Output: String: 42 School
ft_printf("Percent: %%\n");                      // Output: Percent: %

// Integers
ft_printf("Decimal: %d\n", 42);                  // Output: Decimal: 42
ft_printf("Integer: %i\n", -42);                 // Output: Integer: -42
ft_printf("Unsigned: %u\n", 42);                 // Output: Unsigned: 42

// Hexadecimal
ft_printf("Hex (lower): %x\n", 255);             // Output: Hex (lower): ff
ft_printf("Hex (upper): %X\n", 255);             // Output: Hex (upper): FF

// Pointer
int x = 42;
ft_printf("Pointer: %p\n", &x);                  // Output: Pointer: 0x7ffc...

// Mixed
ft_printf("%s scored %d/%d (%x%%)\n", "Bruno", 100, 100, 100);
// Output: Bruno scored 100/100 (64%)
```

---

## <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/Books.png" width="25"/> Key Learnings

<table>
<tr>
<td width="50%">

### 💡 Technical Concepts
- ✅ **Variadic functions** (`va_list`, `va_start`, `va_arg`, `va_end`)
- ✅ **Format string parsing**
- ✅ **Type conversions**
- ✅ **Base conversions** (decimal, hexadecimal)
- ✅ **Pointer manipulation**
- ✅ **Return value tracking**
- ✅ **Modular code design**

</td>
<td width="50%">

### 🎯 Skills Developed
- ✅ **String parsing strategies**
- ✅ **Function pointer usage**
- ✅ **Edge case handling**
- ✅ **Code organization**
- ✅ **Testing methodology**
- ✅ **Documentation writing**
- ✅ **Performance optimization**

</td>
</tr>
</table>

---

## <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/Brain.png" width="25"/> How Variadic Functions Work

```c
#include <stdarg.h>

int ft_printf(const char *format, ...)
{
    va_list args;          // Declare argument list
    
    va_start(args, format); // Initialize the list
    
    // Process each argument based on format specifiers
    // Example: Get an integer argument
    int num = va_arg(args, int);
    
    va_end(args);          // Clean up
    
    return (count);        // Return character count
}
```

---

## <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/Chart%20Increasing.png" width="25"/> Implementation Approach

### 1️⃣ Parse the Format String
```c
while (*format)
{
    if (*format == '%')
        // Handle conversion specifier
    else
        // Print regular character
    format++;
}
```

### 2️⃣ Handle Each Conversion
```c
if (specifier == 'c')
    print_char(va_arg(args, int));
else if (specifier == 's')
    print_string(va_arg(args, char *));
else if (specifier == 'd' || specifier == 'i')
    print_decimal(va_arg(args, int));
// ... and so on
```

### 3️⃣ Track Character Count
```c
int count = 0;

count += write(1, &c, 1);  // Add to count on each write
return (count);             // Return total
```

---

## <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/Magnifying%20Glass%20Tilted%20Left.png" width="25"/> Testing

### Memory Leaks Testing
```bash
# Test with valgrind
valgrind --leak-check=full ./test_program
```

### Comparison Testing
```bash
# Compare with real printf
gcc test.c -o test && ./test
```

### Recommended Testers
- [printfTester](https://github.com/Tripouille/printfTester) - Comprehensive tester
- [ft_printf_tester](https://github.com/paulo-santana/ft_printf_tester) - Another solid option

---

## <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/Pushpin.png" width="25"/> Edge Cases to Handle

<table>
<tr>
<td width="50%">

### 🚨 Critical Cases
- `NULL` strings: `ft_printf("%s", NULL)`
- Empty strings: `ft_printf("%s", "")`
- Zero values: `ft_printf("%d", 0)`
- `NULL` pointers: `ft_printf("%p", NULL)`
- Negative numbers: `ft_printf("%d", INT_MIN)`

</td>
<td width="50%">

### 💡 Tricky Cases
- Multiple specifiers: `ft_printf("%d%d%d", 1, 2, 3)`
- Percent literal: `ft_printf("%%")`
- Single character: `ft_printf("%c", 0)`
- Large numbers: `ft_printf("%u", UINT_MAX)`
- Mixed types: `ft_printf("%s %d %p", "test", 42, &x)`

</td>
</tr>
</table>

---

## <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/Chart%20Increasing.png" width="25"/> Project Stats

```c
typedef struct s_printf_stats {
    int     conversions;        // 9 conversion specifiers
    int     lines_of_code;      // ~500 lines
    int     functions;          // 15+ functions
    int     memory_leaks;       // 0 (Valgrind approved)
    int     norm_errors;        // 0 (Norminette passing)
    int     score;              // 100/125
    char    *difficulty;        // "Medium"
} t_printf_stats;
```

---

## <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/Memo.png" width="25"/> The Norm Compliance

This project strictly follows the 42 School Norm:
- ✅ Maximum 25 lines per function
- ✅ Maximum 80 columns per line
- ✅ Maximum 5 functions per file
- ✅ No forbidden keywords
- ✅ Proper variable declarations
- ✅ No global variables (except static in functions)

---

## <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/Light%20Bulb.png" width="25"/> Design Philosophy

### Modular Architecture
```
ft_printf() → Parse format string
    ├── Handle regular characters
    └── Detect '%' → Route to appropriate handler
        ├── print_char()
        ├── print_string()
        ├── print_decimal()
        ├── print_unsigned()
        ├── print_hex()
        └── print_pointer()
```

### Clean Separation of Concerns
Each conversion type has its own dedicated function, making the code:
- ✅ Easy to understand
- ✅ Easy to test
- ✅ Easy to extend
- ✅ Easy to debug

---

## <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Smilies/Star-Struck.png" width="25"/> What's Next?

After mastering ft_printf, you'll be ready for:
- 📖 **get_next_line** - File I/O and buffer management
- 🎮 **so_long** - Using your ft_printf for game development
- 🔄 **push_swap** - Complex data visualization
- 🐚 **minishell** - Building a complete shell

You can also add ft_printf to your Libft and use it in all future projects!

---

## <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/Link.png" width="25"/> Resources

- [42 ft_printf Subject](https://cdn.intra.42.fr/pdf/pdf/123456/en.subject.pdf)
- [stdarg.h Manual](https://man7.org/linux/man-pages/man3/stdarg.3.html)
- [printf Man Page](https://man7.org/linux/man-pages/man3/printf.3.html)
- [Variadic Functions Tutorial](https://www.cprogramming.com/tutorial/c/lesson17.html)

---

## <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/Mobile%20Phone.png" width="25"/> Contact

**Bruno Gomes** - 42 Porto Student

[![Gmail](https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:brunodrcgomes@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/meetbrunogomes/)
[![42](https://img.shields.io/badge/42-000000?style=for-the-badge&logo=42&logoColor=white)](https://profile.intra.42.fr/users/bramalho)

---

<div align="center">

### 💡 Pro Tips

<img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Smilies/Nerd%20Face.png" width="20"/> **Test with NULL and edge cases first** - They're the most common evaluation traps

<img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Food/Hot%20Beverage.png" width="20"/> **Use helper functions liberally** - Keep functions under 25 lines

<img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Smilies/Star-Struck.png" width="20"/> **Track your return value carefully** - Count every character printed

<img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Smilies/Smiling%20Face%20with%20Sunglasses.png" width="20"/> **Compare with real printf()** - Behavior should match exactly

</div>

---

<div align="center">

### 🏆 Achievement Unlocked!

<img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Activities/Trophy.png" width="60"/>

**Variadic Functions Master - 100/125**

*"Because ft_putnbr() and ft_putstr() aren't enough!"*

<br>

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&height=100&section=footer"/>

</div>
