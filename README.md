# BytesForge 🔥

**Runtime x64 Assembler & Shellcode Factory**  
*Forge shellcode dynamically in C++ - No inline assembly required!*

[![C++](https://img.shields.io/badge/C++-17+-blue.svg)](https://en.cppreference.com/)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/platform-Windows-x64-lightgrey.svg)](https://windows.com)

## 🚀 What is BytesForge?

BytesForge is a header-only C++ library that enables **dynamic x64 assembly generation** at runtime. Perfect for:
- **Shellcode generation**
- **Runtime hooking**  
- **Kernel/Userland payloads**
- **Educational purposes**
- **Red Team operations**

```cpp
#include "BytesForge.hpp"

// Create a polymorphic hook in 3 lines
BytesForge::X64Assembler hook;
hook.MovRax(0x123456789ABCDEF0);
hook.JmpRax();

// Apply hook (12 bytes)
WriteProcessMemory(process, target, hook.GetBytes().data(), 12, nullptr);
```

✨ Features

🛠️ Core Assembly
Full x64 instruction set support

MOV, JMP, CALL, PUSH, POP and more

Register-to-register and immediate operations

Memory operations with complex addressing

🔥 Advanced Capabilities

Polymorphic hook generation - Different code, same result

Function call builders - Windows x64 ABI compliant

Trampoline hooks - Full context preservation

NOP randomization - Anti-pattern evasion

🎯 Use Cases

```cpp
// 1. Simple function hook
auto hook = BytesForge::CreateSimpleHook(0x1337);

// 2. Full trampoline with context save  
auto trampoline = BytesForge::CreateTrampolineHook(
    myHookFunction, 
    returnAddress
);

// 3. Direct function calls
auto call = BytesForge::CreateFunctionCall(
    kernelFunction, arg1, arg2, arg3, arg4
);
```
📦 Quick Start
Installation
```cpp
// Just include the header in your project ! 
#include "BytesForge.hpp"
```

Basic Usage
```cpp
BytesForge::X64Assembler asm;

// Build shellcode dynamically
asm.MovRcx(0x12345678);    // MOV RCX, 0x12345678
asm.MovRax(0xABCDEF00);    // MOV RAX, 0xABCDEF00  
asm.CallRax();              // CALL RAX
asm.Ret();                  // RET

// Execute the generated code
auto shellcode = asm.GetBytes();
ExecuteShellcode(shellcode.data(), shellcode.size());
```
🛡️ Safety Features
Size validation - Automatic fallback for invalid sizes

Exception handling - Protected memory operations

Alignment tools - Proper stack alignment for Windows ABI

Debug logging - Extensive debugging output

📚 Examples
Examples coming soon !

⚠️ Disclaimer
This library is intended for:

Educational purposes

Legitimate security research

Authorized penetration testing

Software development

Use responsibly and only in environments you own or have explicit permission to test.

🤝 Contributing

Found a bug? Want a new feature?

Fork the repository

Create your feature branch

Submit a pull request

📄 License
MIT License - see LICENSE file for details.

🐛 Bug Reports
Open an issue on GitHub with:

Code snippet to reproduce

Expected vs actual behavior

Environment details

BytesForge - Forge your shellcode, master your system. 🔥
