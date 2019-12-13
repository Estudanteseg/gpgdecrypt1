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

# Como utilizar o shell aqui
 gpgdecrypt1.sh -> Decrypt gpg file using brute force. Eg. ./gpgdecrypt1 orato.txt.gpg orato2.txt /usr/share/wordlists/rockyou.txt



