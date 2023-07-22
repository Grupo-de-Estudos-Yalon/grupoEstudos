  
 O TCP é projetado para fornecer uma comunicação confiável e orientada à conexão entre dispositivos, como computadores, servidores, roteadores e outros dispositivos de rede.

Aqui estão algumas características e pontos importantes sobre o TCP:

1. Confiabilidade: O TCP é projetado para garantir que os dados sejam entregues corretamente e em ordem ao destino. Ele usa uma técnica de verificação chamada "acknowledgment" (confirmação), onde o receptor envia uma confirmação de volta ao remetente após receber os dados, indicando que eles foram recebidos com sucesso. Se o remetente não receber essa confirmação, ele retransmite os dados.
    
2. Orientado à conexão: Antes que a transferência de dados possa começar, o TCP estabelece uma conexão entre o remetente e o receptor. Esse processo é conhecido como "handshake de três vias" (three-way handshake). Ele garante que ambos os lados estejam prontos para a transmissão de dados e concordem com os parâmetros de comunicação.
    
3. Fluxo de controle: O TCP gerencia o fluxo de dados entre o remetente e o receptor para evitar sobrecarregar o receptor com mais dados do que ele pode processar. Isso ajuda a garantir um fluxo suave e eficiente de informações.
    
4. Controle de congestionamento: O TCP monitora a quantidade de tráfego de rede e evita congestionamento reduzindo a taxa de transmissão quando necessário. Isso ajuda a manter a estabilidade e a eficiência da rede.
    
5. Tamanho variável de segmento: O TCP divide os dados em unidades chamadas segmentos. O tamanho desses segmentos pode variar dependendo das condições da rede, mas é comum usar o conceito de "MSS" (Maximum Segment Size) para determinar o tamanho máximo do segmento que pode ser enviado em uma conexão TCP.
    
6. Portas: O TCP utiliza números de porta para identificar aplicativos específicos em um dispositivo. As portas ajudam a direcionar os dados para os aplicativos corretos e permitem que vários serviços sejam executados em um único dispositivo.

# Conexão
No entanto, essa garantia de que a informação vai chegar da maneira que foi enviada age como uma espécie de seguro. E seguros tem preços. Numa chamada de vídeo, por exemplo, sempre que um um pacote mínimo de informação, como um frame, se perdesse na comunicação, todo o processo pararia até essa informação chegar. Nesse caso é mais fácil usufruir do [[UDP]] 

No geral, o TCP é fundamental para a transmissão confiável de dados na internet e é amplamente utilizado em várias aplicações, como navegação na web, envio de e-mails, transferência de arquivos e outras atividades que envolvam a comunicação de dados pela rede. Ele trabalha em conjunto com o protocolo [[IP]] (Internet Protocol), que é responsável pelo roteamento dos pacotes na rede. Juntos, TCP e IP formam o conjunto de protocolos TCP/IP, a base da internet moderna.