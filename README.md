# decrypt gpg
# Decriptografar um arquivo que foi criptogrado com gpg utilizando chave simétrica.

# Exemplo de criptografia chave simétrica:

estudante:~/Documents/estudo/crypt/gpg1$ ls


total 12K

drwxr-xr-x 2 estudante estudante 4.0K Oct 23 08:29 .

drwxr-xr-x 3 estudante estudante 4.0K Oct 22 07:07 ..

-rw-r--r-- 1 estudante estudante   35 Oct 22 08:23 orato.txt


estudante:~/Documents/estudo/crypt/gpg1$ cat orato.txt 

o rato roeu a roupa do rei de roma


estudante:~/Documents/estudo/crypt/gpg1$ gpg -c orato.txt 


# Aqui será solicitada uma senha para gerar o arquivo criptografado


estudante:~/Documents/estudo/crypt/gpg1$ ls

total 16K

drwxr-xr-x 2 estudante estudante 4.0K Dec 13 08:29 .

drwxr-xr-x 3 estudante estudante 4.0K Oct 22 07:07 ..

-rw-r--r-- 1 estudante estudante   35 Oct 22 08:23 orato.txt

-rw-r--r-- 1 estudante estudante  108 Dec 13 08:29 orato.txt.gpg


# Veja que foi gerado acima o arquivo orato.txt.gpg cujo conteúdo abaixo está ilegível


estudante:~/Documents/estudo/crypt/gpg1$ cat orato.txt.gpg 

�       �����6��[�T2ŧ�6q�F�h��ׇ���



# Agora vamos ao que interesssa, como rodar o decrypt utilizando força bruta 


# Para garantir vou apagar o arquivo original orato.txt

estudante:~/Documents/estudo/crypt/gpg1$ rm orato.txt


estudante:~/Documents/estudo/crypt/gpg1$ ls

total 12K

drwxr-xr-x 2 estudante estudante 4.0K Dec 13 08:36 .

drwxr-xr-x 3 estudante estudante 4.0K Oct 22 07:07 ..

-rw-r--r-- 1 estudante estudante  108 Dec 13 08:29 orato.txt.gpg


# Como rodar o programa

gpgdecrypt1.sh -> Decrypt gpg file using brute force. Eg. ./gpgdecrypt1 orato.txt.gpg orato2.txt /usr/share/wordlists/rockyou.txt

# Exemplo (parte1), listando os arquivos

estudante:~/Documents/estudo/crypt/gpg1$ ls -lah

total 16K

drwxr-xr-x 2 estudante estudante 4.0K Dec 13 08:46 .

drwxr-xr-x 3 estudante estudante 4.0K Oct 22 07:07 ..

-rwxr-xr-x 1 estudante estudante 1.5K Dec 13 08:46 gpgdecrypt1.sh

-rw-r--r-- 1 estudante estudante  108 Dec 13 08:29 orato.txt.gpg


# Exemplo (parte2), rodando e aguardando até encontrar a senha

estudante:~/Documents/estudo/crypt/gpg1$ ./gpgdecrypt1.sh orato.txt.gpg orato2.txt /usr/share/wordlists/rockyou.txt 

:( Wrong pass 123456 It's bad !!!

:( Wrong pass 12345 It's bad !!!

:( Wrong pass 123456789 It's bad !!!

:( Wrong pass password It's bad !!!

:( Wrong pass iloveyou It's bad !!!

:( Wrong pass princess It's bad !!!

:( Wrong pass 1234567 It's bad !!!

:( Wrong pass rockyou It's bad !!!

:( Wrong pass 12345678 It's bad !!!

:( Wrong pass abc123 It's bad !!!

:::::

:::::

:::::

(aguarde até o final do processamento)

# Exemplo (parte3), senha encontrada

:::::

:::::

:( Wrong pass michael1 It's bad !!!

:( Wrong pass jeffrey It's bad !!!

:( Wrong pass stephen It's bad !!!

****************************************************************

* :D The pass love is the correct. Congrats !!!

* The file orato2.txt was successfully generated !!!

****************************************************************


estudante:~/Documents/estudo/crypt/gpg1$ ls -lah

total 20K

drwxr-xr-x 2 estudante estudante 4.0K Dec 17 05:32 .

drwxr-xr-x 3 estudante estudante 4.0K Oct 22 07:07 ..

-rwxr-xr-x 1 estudante estudante 1.5K Dec 13 08:46 gpgdecrypt1.sh

-rw-r--r-- 1 estudante estudante   35 Dec 17 05:32 orato2.txt

-rw-r--r-- 1 estudante estudante  108 Dec 13 08:29 orato.txt.gpg


# Exemplo (parte4), conferindo o arquivo gerado

estudante:~/Documents/estudo/crypt/gpg1$ cat orato2.txt 

o rato roeu a roupa do rei de roma


