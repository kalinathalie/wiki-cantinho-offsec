# 🌐 Redes de Computadores

Entender como as redes de computadores e seus protocolos funcionam é essencial para uma pessoa analista de segurança. Antes de ser iniciada a listagem de protocolos, é necessário entender que todos eles se encaixam em determinados modelos que ditam as regras de funcionamento, sendo:\
\


<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

O [TCP/IP](https://pt.wikipedia.org/wiki/TCP/IP), que se trata do acrônimo dos protocolos **TCP (Transmission Control Protocol)** e **IP (Internet Protocol)**, é o responsável pela base de envio e recebimento de dados por toda a internet. Essa pilha de protocolos é dividida em 5 camadas (em referência ao [RFC1392](https://www.rfc-editor.org/rfc/rfc1392)):

* **5° Camada - Aplicação**: Serviço específico de comunicação de dados em um nível de processo-a-processo. Exemplo: [HTTP](https://pt.wikipedia.org/wiki/HTTP), [HTTPS](https://pt.wikipedia.org/wiki/HTTPS), [FTP](https://pt.wikipedia.org/wiki/FTP), [DNS](https://pt.wikipedia.org/wiki/DNS).
* **4° Camada - Transporte**: Gerenciamento do transporte dos pacotes para garantir o sucesso no envio e no recebimento de dados. Exemplo: [TCP](https://pt.wikipedia.org/wiki/TCP) e [UDP](https://pt.wikipedia.org/wiki/Protocolo\_UDP).
* **3° Camada - Rede (Internet)**: Endereçamento IP de origem e de destino. Exemplo: [IP](https://pt.wikipedia.org/wiki/Protocolo\_de\_Internet), [ICMP](https://pt.wikipedia.org/wiki/Internet\_Control\_Message\_Protocol), [NAT](https://pt.wikipedia.org/wiki/Network\_address\_translation).
* **2° Camada - Enlace (Ligação)**: Verificação e correção dos dados recebidos do meio físico. Exemplo: [Ethernet](https://pt.wikipedia.org/wiki/Ethernet), [Wi-Fi](https://pt.wikipedia.org/wiki/Wi-Fi).
* **1° Camada - Física**: Especificação dos dispositivos, como hubs e os meios de transmissão, como os cabos de rede.

Já o modelo [OSI](https://www.alura.com.br/artigos/conhecendo-o-modelo-osi) é bastante similar, com a diferença de que a Camada de Aplicação é dividida em 3 partes: **Aplicação, Apresentação** e **Sessão.**\
\
Com o [WireShark](https://www.wireshark.org/) é possível interceptar o tráfego de rede e ver na prática como todas essas camadas trafegam:

<figure><img src="../../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>

Agora vamos dar uma olhada nos principais protocolos:

### IP <a href="#ip" id="ip"></a>

O protocolo **IP** (Internet Protocol) faz parte da camada de internet e é um dos protocolos mais importantes da web. Os destinatários das mensagens são determinados por meio dos campos de endereço IP.

### TCP/UDP <a href="#tcpudp" id="tcpudp"></a>

O protocolo **TCP** (Transmission Control Protocol) é o mais utilizado na camada de transporte para aplicações Web. Em resumo, para estabelecer uma conexão, é utilizado o _three-way handshake_ (acordo de três vias).

<figure><img src="../../.gitbook/assets/image (2) (1).png" alt=""><figcaption></figcaption></figure>

Por conta da demora envolvida no _handshake_ do TCP, o **UDP (User Datagram Protocol)** acaba sendo mais rápido, porém menos seguro. Esse protocolo é o mais usado em softwares de **Streaming** e **VoIP** **(Voice over Internet Protocol)** como o **Discord, Skype, Twitch e Netflix**.

### TLS/SSL <a href="#tlsssl" id="tlsssl"></a>

**Transport Layer Security** **(TLS)** e seu antecessor **Secure Sockets Layer** **(SSL)**, são protocolos de segurança projetados para fornecerem segurança nas comunicações sobre uma rede. Ambos ficam entre a Camada de Aplicação e servem para criptografar as camadas superiores.

### **HTTP/HTTPS** <a href="#httphttps" id="httphttps"></a>

**Hypertext Transfer Protocol \[Secure] (HTTP\[S])** são protocolos base da comunicação Web e a diferença entre eles é que o **HTTPS** utiliza **TLS/SSL** para criptografar a comunicação. É essencial ter total conhecimento sobre todos os seus oito métodos: **GET, HEAD, POST, PUT, DELETE, TRACE, OPTIONS e CONNECT**. Também é necessário conhecer os principais **Headers** de requisição e resposta, e também os **Status-Code** (códigos de retorno):

* 1xx: Informational (Informação).
* 2xx: Success (Sucesso).
* 3xx: Redirect (Redirecionamento).
* 4xx: Client Error (Erro no cliente).
* 5xx: Server Error (Erro no servidor).

### SSH <a href="#ssh" id="ssh"></a>

**Secure Shell (SSH)** é um protocolo de rede criptografado para operação de serviços de rede de forma segura, sua maior utilização é para obtenção de uma shell em algum servidor para a execução de comandos remotamente.

### FTP <a href="#ftp" id="ftp"></a>

**File Transfer Protocol (FTP)** nada mais é do que um protocolo de transferência de arquivos, onde um **Servidor FTP** pode ser acessado tanto pelo terminal, quanto em navegadores.



Essas são apenas algumas das milhares de siglas presentes no dia a dia de uma pessoa analista de segurança, quanto mais conhecimento em redes de computadores, melhor.
