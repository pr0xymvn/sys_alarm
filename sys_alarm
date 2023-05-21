BITS 64


global _sys_alarm

section .rodata
	testt_prt db "Hello world", 10, 0
	testt_prt_len equ $-testt_prt

section .text

_sys_alarm:
	mov rax, 37
	mov rdi, 10
	syscall
	push rax
	jmp _print

_print:
	mov rax, 0x1
	pop rsi
	mov rdi, rsi
	mov rsi, testt_prt
	mov rdi, testt_prt_len
	syscall
	jmp _exit
	
_exit:
	mov rax, 0x3C
	mov rdi, 0
	syscall
