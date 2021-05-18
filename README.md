## Endian Firewall

Endian Firewall es una [distribución de Linux](https://es.wikipedia.org/wiki/Distribuci%C3%B3n_Linux) especializada en Firewall/Proxy que posee una interfaz de administración unificada. Fue desarrollado por la compañia italiana [Endian Srl] (https://es.wikipedia.org/wiki/Sociedad_de_responsabilidad_limitada) y por la comunidad.

Endian Firewall se basó originalmente en [[IPCop](https://es.wikipedia.org/wiki/IPCop), que es una bifurcación del proyecto [Smoothwall] (http://en.wikipedia.org/wiki/SmoothWall).
[Wikipédia](https://es.wikipedia.org/wiki/Endian_Firewall).

![Image](/images/logo.jpg)

- La versión 3.0 contiene los siguientes paquetes y características: 
- Firewall (Bidireccional)
- Gateway
- VPN con OpenVPN o IPsec
- Antivirus Web
- Anti-spam Web
- Antivirus E-Mail
- Anti-spam E-Mail
- Proxy HTTP transparente
- Filtro de contenido
- Punto de acceso inalámbrico seguro
- Protocolo de inicio de sesión - SIP y soporte para VoIP
- Traducción de direcciones de red NAT
- Direcciones IP múltiples (alias)
- Interfaz web HTTPS
- Estadísticas de conexión
- Log de tráfico de redde
- Redirección de Logs a servidor externo
- Servidor DHCP
- Servidor de hora del servidor NTP
- Sistema de detección de intrusos IDS (https://es.wikipedia.org/wiki/Sistema_de_detecci%C3%B3n_de_intrusos)
- Sistema de prevención de intrusiones IPS (https://es.wikipedia.org/wiki/Sistema_de_prevenci%C3%B3n_de_intrusos)
- Soporte de módem ADSL

### Redes de  Endian Firewall

Endian separa las redes conectadas a él en cuatro zonas principales (Red, Green, Blue and Orage), las dos zonas más importantes: VERDE y ROJA.
![Image](/images/zona/zones.png)


- **ROJA**: esto se denomina segmento no confiable, es decir, WAN: cubre todas las redes fuera de Endian, en términos generales, Internet, y es la fuente de las conexiones entrantes. Habilita la configuración del modo failover.

- **VERDE**: la red interna, es decir, la LAN. Esta zona es la más protegida y está dedicada a las estaciones de trabajo y nunca debe accederse directamente desde la zona roja. También es la única zona que, de forma predeterminada, puede acceder a la interfaz de gestión.

- **NARANJA** o **DMZ**: esta zona debe albergar los servidores que necesitan acceder a Internet para brindar servicios (por ejemplo, SMTP / POP, SVN y HTTP). Si un atacante logra romper uno de los servicios / servidores, quedará atrapado dentro de la DMZ y no podrá llegar a la zona verde.

- **AZUL**: Zona Wi-Fi, es decir, la zona que deben utilizar los clientes inalámbricos para acceder a Internet. Las redes inalámbricas a menudo no son seguras, por lo que la idea es aislar a todos los clientes conectados de forma inalámbrica en su propia zona sin acceso a ninguna otra zona, excepto a RED.

### Instalando Endian Firewall

**1** Inicie la computadora con una opción de BOOT a través de CD-ROM, se mostrará la pantalla ISOLINUX, presione ENTER para continuar con la instalación.

![Image](/images/install/install1.jpg)

**2** SSeleccione el idioma inglés, después de elegir, presione TAB para desplazarse hacia abajo hasta el botón OK, luego presione la tecla ENTER. Se le presentará una pantalla de bienvenida y pregunte si desea realizar la instalación de Endian presione ENTER.

![image](/images/install/install2.jpg)

**3** El proximo paso informa que todos los archivos en su disco serán eliminados, proceda con la selección de SÍ y luego presione OK para continuar. Luego se le preguntará si desea habilitar el puerto serie de la computadora para el servicio de consola, la elegimos según, la necesidad y luego OK.

![Image](/images/install/install3.jpg)

**4** Una vez finalizado el proceso de instalación, debemos configurar la dirección IP / MASCARA de la red VERDE. Esta IP se utilizará como puerta de enlace estándar y para acceder a Endian a través de SSH e Interfaz WEB, luego de configurar IP elija la opción OK.

![Image](/images/install/ip.jpg)

**5** Finalmente, aparece una advertencia que indica que expulsa el CD de instalación.

![Image](/images/install/cd.jpg)

### Acesso Web Admin Endian Firewall

Accederemos a la interfaz gráfica de Endian a través de un navegador, será necesario utilizar una máquina cliente. En su navegador escriba ** https: // direccionENDIAN: 10443 **, en el primer inicio de sesión se le informará que hay un problema con el certificado. Simplemente haga clic en continuar en el sitio web no seguro.
![Image](/images/access/acess1.JPG)

**1** Após abrirá a janela inicial clique no botão >>> para continuar.

![Image](/images/access/acess2.JPG)

**2** Escolha o idioma e fuso horário e clique no botão >>> para continuar.

![Image](/images/access/acess3.jpg)

**3** Marque opção que aceita os termos e avance.

![Image](/images/access/acess4.jpg)

**4** Tela seguinte pergunta se você deseja restaurar uma cópia de segurança já existente, apenas clique
 no botão >>> para avençar.

![Image](/images/access/acess5.jpg)

**5** Na próxima janela defina as senhas de administração da interface web e senha de root para acesso
via SSH.

![Image](/images/access/acess6.jpg)

**6** Você deve configurar a ZONA VERMELHA de acordo com serviço fornecido pelo seu provedor de internet.
- ETHERNET STATIC A interface RED recebera um endereço IP estático.
- DHCP ETHERNET A interface RED recebe sua configuração de rede via DHCP (dinâmico).
- PPPoE A interface vermelha está ligado a um modem ADSL. Esta opção só é necessária quando o modem utiliza o modo de bridge e requer usar PPPoE para se conectar ao provedor.
- ADSL (USB, PCI) A interface RED se conecta a um modem ADSL através de um cabo USB ou PCI.
- ISDN A interface VERMELHO é uma ligação RDIS.

![Image](/images/access/acess7.jpg)

**7** Apenas avence janela de configuração das redes LARANJA E AZUL.

![Image](/images/access/acess8.jpg)

**8** Configuração da ZONA VERDE endereço que configuramos na instalação caso queira alterar escolha um novo endereçamento e máscara, digite nome do grupo de trabalho ou
AD.

![Image](/images/access/acess9.jpg)

**9** Próxima configuração escolha servidor DNS para Endian, clique no botão >>> até chegar na opção
OK, APPLY CONFIGURATION para finalizar.

![Image](/images/access/acess10.jpg)

**10** Aguarde um minuto será exibida tela de login do Endian, digite usuário *admin* e senha que foi definida no passo *5*. Endian solicita que você digite endereço de e-mail, apenas ignore clicando em I DON´T WANT ANY UPDATES.

![Image](/images/access/acess11.jpg)

**11** O Dashboard é a página padrão, organizada em duas colunas que fornecem uma visão completa do sistema. As informações visíveis na tela são atualizados em intervalos regulares.

![Image](/images/access/acess12.jpg)

### Status do Sistema

As páginas de status apresenta uma lista completa de informações sobre o estado atual do seu Endian Firewall. A primeira subseção, Status do sistema:
- **Serviços:** Exibe os serviços que estão atualmente em execução.
- **Memória:** Exibe o uso swapfile de memória.
- **Uso de disco:** Mostra a saída do df, que relata a quantidade de total (Tamanho), usado e espaço livre em disco.
- **Uptime e Usuários:** Exibe a saída do w comando que informa o tempo atual, informações sobre o tempo que o sistema tem funcionado sem reinicialização.
- **Módulos carregados:** Isso exibe todos os módulos atualmente carregados e em uso pelo kernel.
- **Kernel Versão:** Exibe informações sobre o próprio Kernel do Endian. Ele exibe versão do kernel.

![Image](/images/status/status1.jpg)

* Status de Rede exibe informações sobre todos os seus dispositivos de rede. Isto inclui PPP, OpenVPN, IPSec, auto-retorno, etc. Basicamente, isto é a saída de ifconfig.

![Image](/images/status/status2.jpg)

* Gráficos sistema clique em um dos gráficos (uso da CPU, uso de memória, uso de troca e acesso ao disco) para obter gráficos de uso por dia, semana, mês e ano.

![Image](/images/status/status3.jpg)

* Tráfego Gráficos esta página dá uma descrição gráfica do tráfego de entrada e de saída. Há seções para cada interface de rede, Verde e Vermelho (Azul e laranja se configurado). Clique em um dos gráficos para mostrar mais gráficos do tráfego nessa interface: por dia, semana, mês e ano.

![Image](/images/status/status4.jpg)

* Gráficos Proxy mostra o tráfego que passou pelo serviço de proxy. Esta informação é útil se o proxy tem o tamanho correto para a carga que está sendo experimentado.

* Ligações Endian Firewall utiliza a instalação firewall Linux Netfilter ou IPTables para manter um firewall stateful. O controle de conexões para todas as ZONAS, com base em ambos os endereços IP de origem e de destino e portas.

![Image](/images/status/status5.jpg)

* Estatísticas de correio SMTP esta página mostra estatísticas gráficos sobre o proxy SMTP Mail.

* Mail Queue exibe a fila de correio atual.

### Network

Esta página é projetada para ajudá-lo a administrar configuração relacionada a rede. Permite configurar entradas de host personalizado. Endian Firewall está executando um proxy DNS chamada dnsmasq, que encaminha todos os pedidos de resolução DNS do seu uplink RED. Isto é muito útil se você quiser criar nomes de máquinas que podem ser resolvidos apenas por seus clientes, mas não pode configurá-los diretamente no seu servidor DNS.

![Image](/images/network/net1.jpg)

- Editor de rotas estáticas é possibilita criar rotas especificas para um endereçamento IP, porta ou uplink especifico.

![Image](/images/network/net2.jpg)

- Gerenciamento de uplink esta página você pode criar regras de failover dos uplinks.

![Image](/images/network/net3.jpg)

### Serviços

Além de sua função principal de firewall de Internet, Eendian pode fornecer uma série de outros serviços que são úteis para uma rede.

![Image](/images/service/serv1.jpg)

- Servidor DHCP (Dynamic Host Configuration Protocol) permite que você controle a configuração de rede de todos os seus computadores ou outros dispositivos da sua rede. Adicionar uma concessão fixa de endereçamento IP, baseado no endereço MAC da placa de rede na máquina.

![Image](/images/service/serv2.jpg)

- DNS dinâmico para usar DYNDNS você deve primeiro registrar um subdomínio com um provedor DYNDNS.

![Image](/images/service/serv3.jpg)

- ClamAV é um antivírus Open Source que pode ser utilizado para escanear todo o tráfego de entrada. Endian Firewall permite configurar as características mais importantes do snort.

![Image](/images/service/serv4.jpg)

- Time Server Administrativo Endian Firewall pode ser configurado para obter o tempo de um timeserver, também pode fornecer esse tempo para outras máquinas em sua rede.

![Image](/images/service/serv5.jpg)

- Sistema de Detecção e Prevenção de Intrusão Endian Firewall contém um poderoso sistema de detecção de intrusão que analisa o conteúdo de pacotes recebidos pelo firewall e pesquisas nas assinaturas conhecidas de actividade maliciosa.

![Image](/images/service/serv6.jpg)

### Firewall

Este recurso é uma das partes mais importantes do Endian Firewall, utiliza Netfilter padrão e cria suas regras bloqueio ou permissão de firewall utilizando iptables.

- Port Forwarding esta subseção permite que você configure as opções de Port Forwarding para Endian Firewall. Suponha que um determinado serviço, por exemplo WEB, em execução num servidor na rede verde, seja acessível por outros dispositivos através da Internet.

![Image](/images/firewall/fw1.jpg)

- Incoming firewall configuration controla o acesso externo. Na imagem a seguir criei uma regra onde bloqueio qual requisitção ICMP proveninente da rede vermelha.

![Image](/images/firewall/fw2.jpg)

- Outgoing Firewall esta subseção permite configurar as regras de firewall de saída. Você pode globalmente permitir o tráfego de saída para RED (Internet) ou definir a única porta para o tráfego de saída. Os seguintes serviços são permitidas por padrão a partir da zona VERDE: HTTP, HTTPS, FTP, SMTP, POP3, IMAP, DNS por padrão é liberado para todas as zonas.
Para remover uma regra, clique no ícone de lixeira . Para editar, clique no ícone de lápis. Para ativar ou desativar uma regra clique no Ativado ícone (a caixa de seleção na coluna ação) para a entrada particular que você deseja ativar ou desativar. O ícone muda para uma caixa vazia quando uma regra é desativado. Clique novamente na caixa de seleção para reativá-lo.

![Image](/images/firewall/fw3.jpg)

- Trafego entre zonas esta subseção permite que você configure as permissões de trafego entre as zonas do Endia, isolando a redes verde das demais.

![Image](/images/firewall/fw4.jpg)

### Proxy HTTP

O servidor proxy é um serviço que funciona como filtro de conteúdo web o cliente se conecta ao servidor proxy, em seguida, solicita uma conexão, arquivo ou outro serviço disponível em um servidor remoto. O proxy fornece ou bloqueia o recurso seja por conexão para o servidor especifico ou a partir de um cache.

**Lista de recursos**
- Autenticação de usuário local, incluindo o gerenciamento de usuários grupo sediado.
- Autenticação LDAP, incluindo MS Active Directory e OpenLDAP.
- Controle de acesso avançado, baseado em rede sobre endereços IP e MAC.
- Acesso baseado em grupos vindos do Active Directory do Windows.
- Restrições de acesso baseados em horário especifico.
- Filtro tipo MIME (extensões de arquivos).
- Bloqueio de navegadores ou software de cliente.

### Configuração do Proxy WEB

Habilitando o proxy permite que o Endian passe a escutar as solicitações sobre a zona seleccionada (verde ou azul ou laranja).
Se o modo transparente está habilitado, todos os pedidos para a porta de destino 80 será encaminhada para o servidor proxy, sem que haja a necessidade de qualquer alterações nas configuração nas maquinas clientes.

**Aviso**
> modo transparente funciona somente para porto de destino 80. Todos os outros pedidos (por exemplo, a porta 443 para SSL) irá
> ignorar o servidor proxy.
Porta proxy, esta é a porta do servidor proxy irá atender pedidos dos clientes, caso configure como proxy não transparente.

**Nota**
> Para reforçar o uso do servidor proxy em modo não-transparente, você terá que bloquear todas as portas de saída normalmente
utilizadas para o tráfego HTTP (80, 443, 8000, 8080, etc.).

![Image](/images/proxy/px1.jpg)

- Hostname visível, se você quer apresentar um nome de host especial em mensagens de erro ou para servidores proxy.
- Cache administrator e-mail, este endereço de e-mail será exibido nas mensagens de erro de servidor proxy. Isto é opcional.
- Linguagem mensagens de erro, selecione o idioma em que as mensagens de erro de servidor proxy será exibido para os clientes.
- Portas permitidas, portas permitidas que vão passar pelo proxy. O resto será bloqueado.

![Image](/images/proxy/px2.jpg)

- Definições do registo estas opções define que arquivos de log de proxy serão gravados.Todos os pedidos de clientes serão gravados em um arquivo de log e pode ser visto dentro do GUI na guia Logs > Proxy.

**Aviso**
> Ativar essa opção pode ser considerado invasão de privacidade pessoal dos seus clientes em alguns países e/ou quebrar outras regras legais. Na maioria dos países, o usuário deve concordar que os dados pessoais serão registrados. Não active, em um ambiente de negócios sem o consentimento por escrito do conselho de trabalhadores.

- Firewall regista ligações de saída assinale esta opção se você deseja que o firewall registre todas as conexões de saída.
- Log termos de consulta a parte da URL contendo consultas dinâmicas serão removidos por padrão antes de iniciar sessão. Ativando a opção de termos de consulta de log vai desligar isso e a URL completa será registrado.
- Log useragents ativando esta opção irá escrever a string useragent no arquivo de log /var/log/squid/useragent.log . Esta opção de arquivo de log só deve ser ativado para fins de depuração e o resultado não é mostrado dentro do visualizador de log baseado em GUI.

![Image](/images/proxy/px3.jpg)

- Gerenciamento de cache parâmetros de controle de cache, tamanho do cache de memória esta é a quantidade de RAM física para ser usado para objetos em cache e em trânsito. Este valor não deve exceder mais de 50% de RAM instalada. O mínimo para esse valor é de 1MB.
- Cache disco rígido quantidade de espaço em disco (MB) a ser usado para objetos em cache.

- Tamanho min objecto, objetos menores do que esse tamanho não será salva no disco. O valor é especificado em kilobytes, e o padrão é 0 KB, o que significa que não há mínimo.

- Tamanho max objecto, objetos maiores do que esse tamanho não será salva no disco. O valor é especificado em kilobytes, e o padrão é 4 MB (4096KB).

- Não armazene domínios uma lista de sites que não serão armazenados em cache. Todos os domínios devem ser inseridos com um ponto à esquerda:

### Configurar um perfil de filtro Web

![Image](/images/proxy/px4.jpg)

Um perfil de Web Filter permite definir listas de domínios/páginas web para ser usado em políticas de acesso. Por um lado, você pode definir uma lista de domínios ou páginas da web que devem ser sempre bloqueados, por outro, é possível permitir que uma ou mais categorias de filtro de URL, para bloquear páginas com base no conteúdo.
Para configurar a filtragem web usando URL Blacklist. Você pode selecionar a categoria para bloquear clicando na seta verde, você pode escolher entre subcategorias e selecionar de forma individual.

![Image](/images/proxy/px5.jpg)

- Você também pode escolher uma lista customizada de sites permitidos ou bloqueados, lista branca ou listas negras. Forneça apenas o nome de domínio (.exemplo.com) com ponto mais a esquerda, nunca use a URLs (https://www.exemplo.com/).

### Configurando a política de acesso

![Image](/images/proxy/px6.jpg)

- O último passo é criar uma política de acesso que irá mapear o perfil de filtragem de conteúdo com base em uma configuração de rede específica. No exemplo acima, estamos criando uma política simples para a **zona verde** toda a rede que está usando o perfil de filtragem de conteúdo **padrão** que foi configurado na etapa anterior.

![Image](/images/proxy/px7.jpg)

- Clique em Criar política, em seguida, aplicar as alterações para finalizar a configuração.

- Você pode testar sua configuração de navegação na Internet a partir da rede verde e você deve ver uma página de bloqueio em sites que correspondem as categorias selecionadas como restrita.

![Image](/images/proxy/px8.jpg)

**Aviso**
>Se você optou por usar proxy não transparente, lembre de definir as configurações em seu navegado. Veja tutorial [clicando aqui.](https://br.ccm.net/faq/28295-como-configurar-o-proxy-no-navegador)

### Logs

![Image](/images/logs/log1.jpg)

A página de visualização de log possuem informações que podem ser exibidas ou exportadas. Por padrão, o visualizador de log sempre mostra a maioria das linhas de log reais como eles aparecem nos arquivos de log do sistema. Os arquivos de log de modo arquivados permanecerá no disco durante 52 semanas até que eles serão apagados.
- Definições do registo página Web Administrativo nesta seção você pode configurar algumas opções úteis. A página é dividida em quatro seções. Cada um deles são descritos abaixo:

![Image](/images/logs/log2.jpg)

- Configurar visualizador de log, define número de linhas, especifica quantas linhas log você deseja que o visualizador exiba em uma página.

- Ordenar em ordem cronológica inversa assinale esta opção se você gostaria que o visualizador de log para exiba as linhas de registo cronologicamente mais recentes primeiro.

![Image](/images/logs/log3.jpg)

- Configuração resumida de Log, resume para x dias define por quantos dias você gostaria de salvar os resumos diários no disco. Nível de detalhe, permite que você decida o nível do resumo dos registros de detalhes. Você pode escolher entre as seguintes possibilidades: baixo, medio, alto. Devido a esta configuração o resumo irá fornecer-lhe com menos mais ou muita informação,.

![Image](/images/logs/log4.jpg)

- Configuração de log remoto, é possível deixar Endian firewall registrar todos os seus arquivos de log também para um servidor syslog remoto. Isto é muito útil se você precisa ter todos os registros de sua empresa em um servidor centralizado de logs e é útil, por exemplo, para ter acesso aos arquivos de log em caso de um desastre. A fim de permitir o registro remoto, você precisa fornecer o nome do host ou endereço IP do servidor syslog remoto no campo de texto chamado servidor Syslog e em seguida, assinale a caixa de seleção Ativado.

![Image](/images/logs/log5.jpg)

- Resumo de Log nesta seção você pode ter uma visão geral dos registros do dia seleccionado.

![Image](/images/logs/log6.jpg)

- Logs de fierwall esta página mostra os pacotes de dados que foram registrados pelo firewall EFW.

> Esta seção contém as entradas para cada um dos pacotes que foram descartados pelo firewall.
* o time do evento.
* a cadeira firewall que foi responsável pela entrada de log.
* a interface (iface) através do qual o pacote veio.
* o protocolo (Proto) utilizados para esse pacote.
* a fonte de endereço IP.
* a porta de origem (porta src).
* o endereço MAC do remetente.
* endereço IP de destino.
* a porta de destino (porta DST).

- Você pode obter informações sobre os endereços IP listados neste log, clicando em um endereço. Endian Firewall executa uma pesquisa DNS e relata qualquer informação disponível sobre seu registro, posse e posição geográfica. Ao clicar em um número de porta que você vai obter algumas informações sobre o serviço que normalmente usa essa porta.

### Sites de referencia

* [Guia de  administração Endian](https://www.endian.com/fileadmin/documentation/efw-admin-guide/en/efw-admin-guide.html) https://www.endian.com/fileadmin/documentation/efw-admin-guide/en/efw-admin-guide.html
* [Help Endian](https://help.endian.com/hc/en-us) https://help.endian.com/hc/en-us
