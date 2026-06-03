+++ 
draft = false
date = 2026-06-03
title = "Some basic assembly functions"
description = ""
authors = ["Sable Ayala"]
tags = ["tech", "blog", "assembly"]
categories = ["technology", "programming"]
series = ["blog"]
math = true
+++

Will add more in the future but just gonna write some basic assembly to show you what it might look like.

# Factorials and Rescursive functions

Below is a demonstration of how to calculate the factorial of a number pushed onto the stack in x86 assembly, the x86_64 will be below

```armasm {linenos=inline}
; calculate the factorial
; 3! = 3 * 2 * 1

; x86 32 bit example

.section .data

.section .text
.globl _start
.globl factorial

_start:
  pushl $4          ; push argument (factorial 4)
  call factorial
  addl $4, %esp     ; scrub parameter, always return SP to where it was before
                    ; we called a function
  movl %eax, %ebx   ; store in ebx as our return status

  movl $1, %eax
  int $0x80

.type factorial, @function
factorial:
  pushl %ebp          ; push so we can restore ebp afterwards
  movl %esp, %ebp     ; we dont want to modify the SP so we push it to ebp
  movl 8(%ebp), %eax
  cmpl $1, %eax
  je end_factorial
  decl %eax
  pushl %eax          ; push it for our call to factorial
  call factorial
  movl 8(%ebp), %ebx  ; reload our parameter in %ebx
  imull %ebx, %eax

end_factorial:
  movl %ebp, %esp ; restoring ebp and esp to where
  popl %ebp       ; they were before the function started

  ret
```

---

```armasm {linenos=inline}
; calculate the factorial
; 3! = 3 * 2 * 1

; x86_64 64bit example

.section .data

.section .text
.globl _start
.globl factorial

_start:
  movl $5, %rdi
  call factorial
  mov %rax, %rdi
  jmp exit

.type factorial, @function
factorial:
  movl %rdi, %rax
  cmpl $1, %rax
  je end_factorial
  decl %rax
  movl %rax, %rdi
  call factorial
  movl %rax, %rbx
  imull %rbx, %rax

exit:
  ret
```

more to come...
