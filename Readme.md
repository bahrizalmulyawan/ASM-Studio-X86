

# ASM Studio

ASM Studio adalah assembler dan emulator Assembly berbasis web yang memungkinkan kode Assembly ditulis, di-assemble, dan dijalankan langsung di browser.

## 🚀 Features

- Assembly editor berbasis web
- Build dan Run langsung di browser
- Emulator CPU berbasis JavaScript
- Dukungan Assembly 8086
- Dukungan Assembly x86 32-bit
- Register viewer
- Memory viewer
- Program output
- Error message dengan nomor baris
- Contoh program siap digunakan
- Source code contoh otomatis menyesuaikan mode CPU

## 🖥️ CPU Modes

ASM Studio menyediakan beberapa mode Assembly melalui dropdown.

### Assembly 8086

Digunakan untuk program Assembly 16-bit.

Contoh:

MOV AX, 10
MOV BX, 20
ADD AX, BX
HLT

### Assembly X86 32-bit

Digunakan untuk program x86 32-bit.

Format dasar:

```asm
.386
.model flat, stdcall
option casemap:none

.data

.code
main PROC

    mov eax, 10
    mov ebx, 20
    add eax, ebx

    ret
main ENDP

END main

🔄 Automatic Example Switching

Contoh program di dropdown otomatis mengikuti mode CPU yang dipilih.

Misalnya pengguna memilih:

Pascal Triangle

kemudian mengubah mode:

Assembly 8086 ↓ Assembly X86

source code Pascal Triangle di editor juga otomatis berubah ke versi x86.

Hal yang sama berlaku untuk contoh lainnya.

📚 Example Programs

ASM Studio menyediakan beberapa contoh program, antara lain:

- Hello World
- Penjumlahan
- Perkalian
- Pembagian
- Faktorial
- Fibonacci
- Pascal Triangle
- Binary
- Luas Lingkaran
- Nilai Pi

Setiap contoh memiliki source code yang disesuaikan dengan arsitektur CPU yang sedang dipilih.

⚙️ X86 Emulator

Mode X86 dijalankan menggunakan CPU virtual berbasis JavaScript.

Instruksi x86 diproses oleh emulator sehingga program dapat dijalankan langsung dari browser tanpa membutuhkan:

- MASM
- NASM
- Visual Studio
- Command Prompt
- File ".bat"
- Compiler eksternal

Register X86

Emulator menggunakan register 32-bit seperti:

EAX EBX ECX EDX ESI EDI EBP ESP EIP

📐 X86 Directives

Source X86 mendukung struktur MASM-style seperti:

.386
.model flat, stdcall
option casemap:none

Directive tersebut digunakan untuk menentukan target Assembly dan model memory.

➗ Arithmetic

ASM Studio mendukung operasi aritmatika pada mode X86, termasuk:

ADD
SUB
MUL
DIV
INC
DEC

Contoh:

mov eax, 100
mov ebx, 5

div eax, ebx

Hasil operasi tersedia melalui register emulator.

🔀 Control Flow

Program dapat menggunakan instruksi branching dan looping yang tersedia pada emulator, misalnya:

CMP
JMP
JE
JNE
JG
JL
JGE
JLE
LOOP

Contoh:

mov eax, 0

loop_start:
    inc eax
    cmp eax, 10
    jl loop_start

🧮 Example: Factorial

Contoh perhitungan factorial menggunakan mode X86:

.386
.model flat, stdcall
option casemap:none

.code

main PROC
    mov eax, 1
    mov ecx, 6

factorial_loop:
    mul eax, ecx
    dec ecx
    cmp ecx, 1
    jg factorial_loop

    ret
main ENDP

END main

Hasil:

720

🔢 Example: Pascal Triangle

ASM Studio juga menyediakan implementasi Pascal Triangle menggunakan operasi aritmatika dan looping pada emulator X86.

Contoh output:

1
1 1
1 2 1
1 3 3 1
1 4 6 4 1
1 5 10 10 5 1
1 6 15 20 15 6 1
1 7 21 35 35 21 7 1

🔢 Example: Binary

Program Binary digunakan untuk mengubah nilai integer menjadi representasi biner.

Contoh:

Decimal : 8
Binary  : 0000000000001000

🛠️ Cara Menggunakan

1. Buka ASM Studio di browser.
2. Pilih mode Assembly dari dropdown.
3. Pilih contoh program atau tulis kode sendiri.
4. Klik Build.
5. Jika tidak ada error, klik Run.
6. Lihat hasil pada Program Output.
7. Gunakan Registers dan Memory untuk melihat keadaan CPU.

❌ Error Handling

Jika assembler menemukan kesalahan, ASM Studio menampilkan:

line <number>: <error message>

Contoh:

line 22: unsupported x86 instruction 'XYZ'

Nomor baris dapat digunakan untuk menemukan instruksi yang menyebabkan error.

🌐 Browser Based

ASM Studio dirancang untuk berjalan langsung di browser.

Tidak diperlukan instalasi compiler Assembly eksternal untuk menggunakan emulator.

Seluruh proses:

Source Code
     ↓
Assembler
     ↓
Machine Code
     ↓
Virtual CPU
     ↓
Program Output

dijalankan di dalam aplikasi web.

📁 Project Structure

Struktur project secara umum:

ASM-Studio/
│
├── index.html
├── README.md
├── assets/
├── examples/
└── scripts/

File contoh Assembly dapat ditempatkan di folder:

examples/

⚠️ Limitations

ASM Studio adalah emulator edukasi berbasis web, bukan implementasi penuh prosesor Intel x86.

Tidak semua instruksi dan fitur x86 tersedia.

Beberapa fitur seperti:

- hardware interrupt
- protected-mode OS
- privilege levels
- native device access
- real hardware I/O
- seluruh instruction set Intel x86

tidak disimulasikan.

Instruction set yang tersedia bergantung pada implementasi emulator ASM Studio.

🎓 Purpose

ASM Studio dibuat untuk membantu pembelajaran:

- Assembly
- CPU architecture
- Registers
- Memory
- Machine instructions
- Arithmetic operations
- Control flow
- Assembler
- Emulator

Dengan ASM Studio, pengguna dapat mempelajari bagaimana kode Assembly diproses oleh CPU tanpa harus memasang toolchain Assembly secara manual.

📄 License

Tambahkan lisensi project sesuai kebutuhan project ini.


---

ASM Studio — Web-based Assembly IDE & CPU Emulator
