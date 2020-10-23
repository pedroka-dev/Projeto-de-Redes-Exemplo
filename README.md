# Introdução
Uma proposta de Projeto de Rede (Projeto Lógico, Projeto Físico e Modelo de Simulação no PacketTracer) para um ambiente hipotético. Este repositório representa como seria apresentado um projeto de redes para um cliente hipotético, sendo nesse caso uma Escola Pública de Educação Básica do Município.

# Expecificações
<b>Cliente</b>: Escola Pública de Educação Básica do Município

<b>Objetivo</b>: Dimensionamento, instalação e configuração da rede lógica da escola.

# Sales Pitch

Este projeto de rede tem como foco o equilibrio entre performance e custo, se adaptando as necessidades do cliente, visando a escalabilidade e providenciando diversas opções financeiras, enquanto ainda mantem qualidade e performance de rede. 

Diversos serviços são disponibilizados, como configuração automatica de IP em novos dispositivos da rede, implementação de um servidor para websites, email customizavel com domínio da escola, entre outros.


Dentre as opções disponíveis de acordo com a necessidade do cliente, é possível escolher velocidade utilizando cabeamento de fibra optica e dois acess points, ou opcionalmenteum um custo menor, com o padrão cat6 em conjunto com dois repeaters.

Se caso for de desejo do cliente, é também possivel diminuir ainda mais o custo, com a utilização de um computador comum como servidor para os serviços prestados.Apesar desta opção não ser recomendada no quesito desempenho, esta é mais uma das escolhas disponibilizadas para melhor se adaptar ao bolso do cliente.


A rede após sua implemtanção não só possuirá cabeamento funcional e altamente organizado nolaboratório, direção e secretaria, mas também  umarede sem fio disponivel para as salas de aula e os 4 corredores do prédio.

---

# Topologia (Packet Tracer)
![alt text](https://raw.githubusercontent.com/pedro-ca/Projeto-de-Redes-Exemplo/master/Imagens/topologia%20completa.JPG)

# Requisitos Iniciais: Situação Física

  - <b>Secretaria (Piso 1)</b>: 

    - 2 computadores
    - 1 impressora de rede (laser).


  - <b>Direção (Piso 1)</b>: 
    - 1 computador
    - 1 impressora jato de tinta.
 
 
  - <b>Corredores 1 e 2 (Piso 1)</b>: 
    - 50 metros de comprimento cada corredor
    - 8 salas de aula em cada corredor.


  - <b>Corredores 3 e 4 (Piso 2)</b>: 
    - 50 metros de comprimento cada corredor 
    - 8 salas de aula em cada corredor.


  - <b>Laboratório de Informática</b>: 
    - 30 computadores.


# Requisitos Iniciais: Situação Lógica
Cabeada ligando os computadores e rede sem fio disponibilizada nos corredores e salas de aula. 
Serviços disponíveis:
  - DHCP
  - WEB
  - Server DNS
  - SSH
  - E-MAIL (SMTP);


# Pseudo-Planta da Escola para referencia
![alt text](https://raw.githubusercontent.com/pedro-ca/Projeto-de-Redes-Exemplo/master/Imagens/pseudoplanta%20piso%201.png)
![alt text](https://raw.githubusercontent.com/pedro-ca/Projeto-de-Redes-Exemplo/master/Imagens/pseudoplanta%20piso%202.png)


---

# Análise: Situação Física
*TOPOLOGIA DE CABEAMENTO*: Cabeamento

*CABOS UTILIZADOS*
  - Cabeamento Backbone: Fibra Monomodo(+ Conversores de Mídia de Fibra Óptica); Como o Cabeamento Backbone não é tão extensivo em termos de comprimento, a Fibra Monomodo se torna uma opção viável(Não serão necessários muito mais do que 10m de fibra);
    - Alternativa: Cabo STP Cat6; Preço mais acessível, sem muita perda na performance. Para o Cabeamento Backbone(Vertical), não é necessário muito comprimento de cabo.
  - Cabeamento Horizontal: UTP/STP Cat6, levando como preferência STP para áreas com muita interferência e UTP para áreas com pouca interferência.
    - STP se torna a opção mais viável para todo o projeto, devido a quantidade imensa de dispositivos telefônicos + dispositivos com acesso a tecnologias Wireless em 2.4GHz.
    
*TECNOLOGIAS*:
 - Gigabit Ethernet: Fast Ethernet está virando uma tecnologia legado. Com isso em mente, é mais lucro visar a implementação de tecnologias GigabitEthernet e 10GigabitEthernet para poder tomar mais proveito disso no futuro, sem ter que ser necessário uma reforma nessa área; Contudo, o Gigabit Ethernet não precisa ser utilizado em todo o projeto.
    - DISCREPÂNCIA: O projeto lógico foi feito em majoritariamente com FastEthernet; Em um contexto de vida real, onde foi usado GigabitEthernet no projeto do PacketTracer pode ser substitudo pela tecnologia 10GigabitEthernet, e onde foi usado FastEthernet, GigabitEthernet.
    - A tecnologia 10GigabitEthernet requer cabos adequados para a sua implementação, aumentando em mais ainda o custo do projeto (Normalmente requer fibra multimodo ou monomodo);
 - Tecnologia WAN: Não definida. (Depende muito do Provedor de Serviços de Internet);
        
        
*EQUIPAMENTOS*:
 - Preço total médio: R$7,812.50;
 - ATIVOS:
   - NoBreak(1 un):
   
                • ~R$500;
                • Necessário para o server e para os equipamentos mais importantes.
                
   - Access Points(2un no projeto):
   
                • UAP AC Lite - R$600 Distância: 122m, 300 Mbps(2,4GHz), 867Mbps(5GHz);
                • UAP AC LR - R$800; Distância: 183m, 450 Mbps(2,4GHz), 867Mbps(5Ghz);
                • Alternativa: Repetidores; Repetidores são alternativas de custo menor aos Access Points. Seriam necessários 4 repetidores ao todo para cobrir todos os 4 corredores.
                
   - Roteador(1un no projeto):
   
                • R$50-300;
                
   - Server(1un no projeto):
   
                • R$2,200-5,000;
                • Alternativa: Empresas de hospedagem de servidores dedicados/não dedicados(Preço é dado mensalmente, através de uma assinatura);
                • Alternativa: Computador com um server; Mais eficiente em termos de custo.
                
   - Switch(3un* no projeto):
   
                • 16 Portas Cat6: R$150-400;
                • 24 Portas Cat6: R$300-600;
                • 48 Portas Cat6: ~R$1000;
                • *Devem haver switches suficientes para acomodarem em torno de 40 cabos; 30 computadores no laboratório, 10 para o resto do projeto.
                
   - Passivos:
   
                • Rack(2un):
                    ◦ R$250-500;
                • Patch Panel(2un):
                    ◦ 12 Portas: ~R$50-100 Cat6
                    ◦ 24 Portas: ~R$150 Cat6
                • CABOS:
                    ◦ Conectores RJ45 Cat6
                        ▪ R$25-30 por 100un;
                    ◦ Fibra Monomodo:
                        ▪ Conversor de Mídia: ~R$100;
                        ▪ ~R$20 por 10m, ~R$50-200 por 100m;
                    ◦ Cabo UTP Cat6:
                        ▪ R$40 por 10m;
                    ◦ Cabo STP Cat6:
                        ▪ R$250 por 150m; R$200 por 100m;
                        

# Análise: Situação Lógica 

  - Topologia Lógica: Utilizando Packet Tracer</b>
    - Topologia Completa:
    
     ![alt text](https://raw.githubusercontent.com/pedro-ca/Projeto-de-Redes-Exemplo/master/Imagens/topologia%20completa.JPG)
     
    - Topologia Lógica do Laboratório:
    
     ![alt text](https://raw.githubusercontent.com/pedro-ca/Projeto-de-Redes-Exemplo/master/Imagens/topologia%20laboratorio.JPG)
     
    - Topologia Lógica da Secretaria:
    
     ![alt text](https://raw.githubusercontent.com/pedro-ca/Projeto-de-Redes-Exemplo/master/Imagens/topologia%20secretaria.JPG)
     
    - Topologia Lógica da Direção:
    
     ![alt text](https://raw.githubusercontent.com/pedro-ca/Projeto-de-Redes-Exemplo/master/Imagens/topologia%20direcao.JPG)
     
   - Topologia Lógica dos Corredores e rede sem fio:
    
![alt text](https://raw.githubusercontent.com/pedro-ca/Projeto-de-Redes-Exemplo/master/Imagens/topologia%20corredores%20e%20rede%20sem%20fio.JPG)
     
  - DNS: Serviço do Domain Name System contido no servidor 192.168.0.2, de nomenclatura no DNS como “dns”. Estão registrados os seguintes endereços:
    - “dhcp”, “dns”, “tftp”, “webserver” para o IP 192.168.0.2
    - “router” para o IP 192.168.0.1
    - “printerdire” para o IP 192.168.0.3
    - “printersecr” para o IP 192.168.0.4
    
     ![alt text](https://raw.githubusercontent.com/pedro-ca/Projeto-de-Redes-Exemplo/master/Imagens/packet%20tracer%20dns.JPG)
         
  - HTTP: Serviço do Webserver contido no servidor 192.168.0.2, de nomenclatura no DNS como “webserver”. Web server pode ser acessado por qualquer integrante da rede.
  
     ![alt text](https://raw.githubusercontent.com/pedro-ca/Projeto-de-Redes-Exemplo/master/Imagens/packet%20tracer%20http.JPG)
         
  - DHCP: Serviço de Dynamic Host Configuration Protocol contido no servidor 192.168.0.2, de nomenclatura no DNS como “dhcp”. Em sua configuração, aponta como gateway o IP 192.168.0.1 e automaticamente seleciona o IP de novos integrantes da rede a partir de 192.168.0.5.
  
     ![alt text](https://raw.githubusercontent.com/pedro-ca/Projeto-de-Redes-Exemplo/master/Imagens/packet%20tracer%20dhcp.JPG)
         
  - EMAIL: Serviço de Simple Mail Transfer Protocol contido no servidor 192.168.0.2, de nomenclatura no DNS como “email”. Utiliza o domain “escola.com” e permite com que usuários previamente registrados e logados em um computador enviar emails.
  
     ![alt text](https://raw.githubusercontent.com/pedro-ca/Projeto-de-Redes-Exemplo/master/Imagens/packet%20tracer%20email.JPG)
         
  - SSH: Serviço de Secure Shell contido no roteador 192.168.0.1, de nomenclatura no DNS como “router”. Permite conexão segura com o servidor SSH depois do login através de uma máquina remota.
  
Configurações realizadas no CLI do terminal:
<details>
 
    Router>enable
    Router#conf t
    Enter configuration commands, one per line.  End with CNTL/Z.
    Router(config)#interface gigabitethernet 0/0
    Router(config-if)#no shutdown
    Router(config-if)#
    %LINK-5-CHANGED: Interface GigabitEthernet0/0, changed state to up

    %LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/0, changed state to up

    Router(config-if)#exit
    Router(config)#hostname ADMIN
    ADMIN(config)#ip domain-name admin.com
    ADMIN(config)#crypto key generate rsa

    The name for the keys will be: ADMIN.admin.com
    Choose the size of the key modulus in the range of 360 to 2048 for your	General Purpose Keys. Choosing a key modulus greater than 512 may take a few minutes.

    How many bits in the modulus [512]: 1024
    % Generating 1024 bit RSA keys, keys will be non-exportable...[OK]

    ADMIN(config)#
    *mar 1 0:3:26.678:  %SSH-5-ENABLED: SSH 1.99 has been enabled
    ADMIN(config)#ip ssh version 2
    ADMIN(config)#ip ssh authentication-retries 3
    ADMIN(config)#ip ssh time-out 30
    ADMIN(config)#username cisco privilege 15 password cisco 123
    ADMIN(config)#line vty 0 4
    ADMIN(config-line)#login local
    ADMIN(config-line)#privilege level 15
    ADMIN(config-line)#transport input ssh
    ADMIN(config-line)#end
    ADMIN#
    %SYS-5-CONFIG_I: Configured from console by console
</details>
  


    
