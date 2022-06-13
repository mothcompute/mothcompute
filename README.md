```
[org 0x7c00]

mov ax, 0x13
int 10h

xor bx, bx
mov di, bx
mov cx, bx
push 0xA000
pop es

l:      mov ch, 0x32
        mov al, [c+bx]
        or al, al
        jz $
        inc bl
        rep stosb
        jmp l

c:      db 11, 13, 15, 13, 11

times 510-($-$$) db 0
dw 0xAA55
```
