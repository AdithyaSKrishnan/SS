data segment
    msg1 db 10,13,'Enter String $'
    msg2 db 10,13,'String is a palindrome$'
    msg3 db 10,13,'String is not a palindrome$'
    str1 db 50 dup(0)
data ends
code segment
    assume cs:code, ds:data
    start:
        mov ax,data
        mov ds,ax
        lea dx,msg1
        mov ah,09h
        int 21h
        
        lea si,str1
        lea di,str1
    next:
        mov ah,01h
        int 21h
        cmp al,13
        je terminate
        mov [di],al
        inc di
        jmp next
    terminate:
        mov al,'$'
        mov [di],al
        dec di
    dothis:
        mov al,[si]
        cmp al,[di]
        jne notpalindrome
        inc si
        dec di
        cmp si,di
        jl dothis
    palindrome:
        lea dx,msg2
        mov ah,09h
        int 21h
        jmp endprogram
    notpalindrome:
        lea dx,msg3
        mov ah,09h
        int 21h
    endprogram:
        mov ah,4ch
        int 21h
    code ends
end start
