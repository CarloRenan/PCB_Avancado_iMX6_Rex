# Como o circuito funciona

O conjunto **iMX6 Rex + Development Baseboard** forma uma plataforma de computação embarcada. O módulo compacto executa os programas; a placa base oferece alimentação e conexões para telas, rede, armazenamento e periféricos. Pode ser utilizado no desenvolvimento de uma interface gráfica, de um equipamento conectado ou de uma aplicação de controle. A função final depende do software instalado.

![Conjunto montado em 3D](../Imagens/Conjunto_3D.png)

*Vista mecânica de referência: o módulo sobre a base é o modelo M1 incorporado ao arquivo da base. As vistas individuais da [galeria](../Imagens/README.md) usam o arquivo de cada etapa do curso.*

## 1. Módulo: processamento e memória

O módulo mede **70 × 40 mm** e possui **12 camadas de cobre**. Nele ficam o processador, a memória DDR3, a flash e os circuitos necessários para alimentar e interligar esses blocos.

| Bloco | Referência e componente no módulo | Função |
|---|---|---|
| Processador | U1 — MCIMX6Q5EYM10AC | Executa instruções e controla interfaces. Os parâmetros do esquemático indicam ARM Cortex-A9, quatro núcleos de 32 bits e 1,0 GHz. |
| Memória DDR3 | U2–U5 — MT41J128M16HA-15E:D TR | Guarda programas e dados durante a execução. Quatro componentes de 2 Gbit somam 1 GiB, usualmente indicado como 1 GB. |
| Flash SPI | U10 — SST25VF016B-75-4I-QAF | Memória não volátil de 16 Mbit, equivalentes a 2 MiB. O esquemático inclui uma referência a uBoot, relacionada à inicialização. |
| Ethernet PHY | U8 — KSZ9021RN | Implementa a interface física Ethernet 10/100/1000, em conjunto com o controlador do processador. |
| Supervisão | U6 — TPS3808G09DBVR | Monitora alimentação e participa do circuito de reset. |
| Fontes | U11/U13 — ISL6236AIRZ; U12 — TPS62175DQCT; U9 — MIC33050-4YHL TR | Com indutores, capacitores e componentes associados, fornecem as tensões dos diferentes blocos. |
| Interligação | J1/J2 — QSH-030-01-L-D-A | Conectores de 60 posições que transportam alimentação e sinais entre as placas. |

A **DDR3 é a memória de trabalho**: perde o conteúdo ao desligar. A **flash conserva dados**, mas possui capacidade muito menor. A memória usada para executar programas, o código de inicialização e o armazenamento do sistema cumprem funções diferentes.

As capacidades e velocidades acima descrevem os componentes selecionados nos esquemáticos. Não são resultados de testes de desempenho desta entrega.

## 2. Placa base: interfaces externas

A base mede **135 × 110 mm** e possui **6 camadas de cobre**. Os conectores J1/J2, do tipo QTH-030-01-L-D-A, recebem o módulo. Os designadores desta tabela pertencem à base; U1 da base, por exemplo, é um componente diferente de U1 do módulo.

| Interface | Componentes ou conectores | Para que serve |
|---|---|---|
| HDMI | J16; U7 — CM2020-00TR | Conexão de vídeo digital; U7 participa da interface e proteção da porta. |
| LVDS | J41 e circuitos da folha `[08]` | Ligação de painel de vídeo e sinais associados à iluminação. |
| USB | J22, J20/J23, J21; U13 — USB2514BI-AEZG | Portas e headers USB, hub e micro USB OTG. U11/U12 controlam a distribuição de energia das portas. |
| Ethernet | J24 | Conector da rede com fio, associado ao PHY localizado no módulo. |
| SATA / CFast | J14 / J15 | Conexão de armazenamento, conforme a configuração do projeto. |
| microSD | J29 / J39 | Armazenamento removível para arquivos ou software compatível com a configuração de inicialização. |
| Expansão | J4 / J9; J3 | Encaixes no formato mini PCIe e conector PCIe adicional. Os dois encaixes mini possuem funções diferentes. |
| Áudio principal | U14 — SGTL5000XNAA3R2; J25–J28 | Conversão de áudio digital/analógico e conectores de fone, linha e microfone. |
| Áudio auxiliar | U5 — MAX9867ETJ+; U4 — TPA6041A4RHBR | Codec e amplificador no bloco de áudio associado à segunda expansão. |
| Comunicação serial | J30/J31; U16 — ISL4245EIRZ | UART e adaptação de níveis RS-232 para comunicação e depuração. |
| Relógio e configuração | U17 — PCF8563T; U18 — BR24L02; J32 | Relógio de tempo real, EEPROM e suporte para bateria do relógio. |
| GPIO e toque | U19 — PCA9535; U2 — TSC2007; J40 | Expansão de entradas/saídas digitais e interface de touchscreen. |
| Alimentação | J37/J38; U22 — ISL6236AIRZ | Entrada de energia e fontes de 5 V e 3,3 V identificadas na folha `[16]`. |

A documentação do projeto distingue **um encaixe mini PCIe com PCIe, USB e SIM** e **outro com USB, SIM e suporte de voz**. O formato mecânico semelhante não significa dois canais PCIe independentes. Wi-Fi ou modem dependem da placa de expansão instalada. [Descrição oficial da base](https://sites.google.com/imx6rex.com/www/application/imx6-development-board).

## 3. Exemplo do caminho dos dados

Em uma aplicação com tela, o processador executa o programa usando a DDR3, recebe comandos dos periféricos e envia a imagem por HDMI ou LVDS. Arquivos podem vir do armazenamento ou da rede. A base fornece os conectores e os circuitos de interface desses caminhos.

Conceitualmente, a partida envolve estabilizar as fontes, liberar o reset, iniciar o processador conforme a configuração de boot e carregar o software. Os jumpers, as mídias e a sequência exata devem seguir os esquemáticos e o manual da revisão utilizada. Este pacote não inclui firmware executável nem registro de teste de partida.

## 4. O que o curso exercita

As interligações DDR3, HDMI, LVDS, SATA, PCIe, USB e Ethernet exigem cuidados de posicionamento e roteamento. Comprimento e espaçamento das trilhas, planos de referência e empilhamento afetam a propagação dos sinais. As atividades trabalham esses aspectos, além da distribuição de alimentação e dos capacitores de desacoplamento.

A última etapa encontrada para o módulo é **L7-02 — Impedance Adjustment**. Para a base, é **L7-01 — Differential Pairs Fine Tuning**. A aparência das imagens não comprova aprovação de fabricação: a conferência final exige abrir os projetos no Altium, confirmar a variante e executar as verificações aplicáveis.

## Onde conferir

- **Designadores e componentes:** [esquemáticos originais](../Projetos/) e [BOM](../BoM/).
- **Posições, dimensões e camadas:** documentos `.PcbDoc` e [galeria 2D/3D](../Imagens/README.md).
- **Contexto da plataforma:** [iMX6 Rex](https://sites.google.com/imx6rex.com/www/home) e [Development Baseboard](https://sites.google.com/imx6rex.com/www/application/imx6-development-board).
- **Escopo dos arquivos e preparação para fabricação:** [origem](ORIGEM.md) e [critérios da entrega](ENTREGA.md).
