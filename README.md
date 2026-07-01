# FASM - for idiots (for me)

najpierw trza zapisać rodzaj pliku do jakiego kompilujemy ELF64 dla linux PE dla windows

pamiętaj bo zapomnisz lol tu będzie na linux

```
format ELF64 executable 3
entry start
```

tu jest że kompilujesz do linux i zaczynasz od label start

```
format ELF64 executable 3 
entry start

start:
    mov rax, 60
    mov rdi, 0
    syscall
```

co jest odpowiednikiem

```cpp
int main() {
   return 0;
}
```

mov rax, 60

znaczy że ten odpalasz syscall Exit a raczej przekazujesz do rejestru `rax` wartość 60 bo mov działa tak

mov `<cel>`,  `<zródło>`
to znaczy

mov `rejestr`, `wartość`

## HELLO WORLD w konsoli

```
format ELF64 executable 3 
entry start

start:
    mov rax, 1 ; bo 1 to sys_write
    mov rdi, 1 ; bo 1 to stdout czyli standardowe wyjście
    mov rsi, msg
    mov rdx, msg_len
    syscall

    mov rax, 60
    mov rdi, 0
    syscall

msg db 'Hello, world', 10
mag_len = $ - msg
```
    


