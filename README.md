# PCB Avançado — iMX6 Rex

**Aluno:** Carlos Renan  
**Curso:** Advanced PCB Layout Course

Neste trabalho, apresento o estudo do módulo **iMX6 Rex** e da **Development Baseboard**, com foco na arquitetura do circuito, no layout de placas multicamadas e nas interligações de alta velocidade. A documentação reúne os projetos Altium, as vistas 2D e 3D, a lista de materiais e o orçamento de fabricação e montagem.

![Conjunto iMX6 Rex e Development Baseboard em 3D](PCB_Avancado/Imagens/Conjunto_3D.png)

*Conjunto iMX6 Rex e Development Baseboard — vista mecânica de referência.*

[Funcionamento do circuito](PCB_Avancado/docs/FUNCIONAMENTO.md) · [Projetos Altium](PCB_Avancado/Projetos/) · [Galeria 2D/3D](PCB_Avancado/Imagens/README.md) · [BOM](PCB_Avancado/BoM/README.md) · [Cotação JLCPCB](PCB_Avancado/Cotacao/README.md)

## Objetivo

Estudar o projeto de uma plataforma de computação embarcada, relacionando as funções dos componentes às decisões de posicionamento e roteamento da PCB. Os principais temas são o controle de impedância, o ajuste de pares diferenciais, a interligação da memória DDR3 e a distribuição de alimentação.

## Arquitetura do circuito

O **módulo iMX6 Rex** concentra o processador, a memória e os circuitos essenciais de processamento. A **Development Baseboard** recebe o módulo e oferece alimentação e conexões para vídeo, rede, armazenamento, áudio e periféricos.

| Parte | Função | Etapa do curso |
|---|---|---|
| Módulo iMX6 Rex | Processamento, memória DDR3, flash e interface Ethernet | L7-02 — Impedance Adjustment |
| Development Baseboard | Alimentação e interfaces externas | L7-01 — Differential Pairs Fine Tuning |

O módulo utiliza o processador **MCIMX6Q5EYM10AC**, quatro memórias **MT41J128M16HA-15E:D TR**, o PHY Ethernet **KSZ9021RN** e a flash SPI **SST25VF016B-75-4I-QAF**. Os conectores J1/J2 transportam alimentação e sinais entre as duas placas.

A base disponibiliza HDMI, LVDS, USB, Ethernet, SATA/CFast, PCIe, áudio, microSD, UART e GPIO. Essa arquitetura permite desenvolver aplicações com interface gráfica, comunicação em rede e controle de periféricos. O comportamento da aplicação é definido pelo software embarcado.

A [descrição do funcionamento](PCB_Avancado/docs/FUNCIONAMENTO.md) detalha os componentes, as interfaces e o caminho dos dados.

## Características das placas

| Característica | Módulo | Placa base |
|---|---:|---:|
| Dimensões | 70 × 40 mm | 135 × 110 mm |
| Camadas de cobre | 12 | 6 |
| Componentes com código de fabricante na BOM | 457 | 546 |
| Grupos de componentes na BOM | 66 | 124 |

## Vistas 3D

| Módulo — face superior | Módulo — face inferior |
|---|---|
| ![Módulo em 3D, face superior](PCB_Avancado/Imagens/Modulo_3D_superior.png) | ![Módulo em 3D, face inferior](PCB_Avancado/Imagens/Modulo_3D_inferior.png) |

| Placa base — face superior | Placa base — face inferior |
|---|---|
| ![Placa base em 3D, face superior](PCB_Avancado/Imagens/Placa_base_3D_superior.png) | ![Placa base em 3D, face inferior](PCB_Avancado/Imagens/Placa_base_3D_inferior.png) |

## Layout das PCBs

![Vistas superior e inferior do módulo e da placa base](PCB_Avancado/Imagens/PCB_Avancado_Layouts.png)

*Trilhas externas, pads, vias e contornos. Faces inferiores vistas por baixo; comparação sem escala comum entre as placas.*

## Documentação

| Conteúdo | Acesso |
|---|---|
| Projetos, esquemáticos e layouts Altium | [Projetos](PCB_Avancado/Projetos/) |
| Descrição dos blocos e interfaces | [Funcionamento do circuito](PCB_Avancado/docs/FUNCIONAMENTO.md) |
| Vistas do conjunto e das duas faces de cada PCB | [Galeria 2D/3D](PCB_Avancado/Imagens/README.md) |
| Lista de materiais em Excel e CSV | [BOM](PCB_Avancado/BoM/README.md) |
| Orçamento de fabricação e montagem | [Cotação JLCPCB](PCB_Avancado/Cotacao/README.md) |
| Objetivos e conteúdo do trabalho | [Apresentação acadêmica](PCB_Avancado/docs/ENTREGA.md) |
| Projeto de referência e bibliografia | [Referências](PCB_Avancado/docs/ORIGEM.md) |

## Fabricação e montagem

| Item | Quantidade | Valor (USD) |
|---|---:|---:|
| PCB do módulo | 5 | US$ 510,03 |
| PCB da placa base | 5 | US$ 43,50 |
| Montagem da placa base nos dois lados | 2 | US$ 330,53 |
| **Subtotal, sem frete e tributos** | — | **US$ 884,06** |

O orçamento da JLCPCB contempla a fabricação das duas PCBs e a montagem de duas unidades da placa base. O serviço de montagem do módulo HDI está indisponível nessa cotação. O frete apresentado para o módulo é de **US$ 42,51**, separado do subtotal.

[Especificações, prazos e orçamento detalhado](PCB_Avancado/Cotacao/README.md).

## Consulta no Altium Designer

| Placa | Projeto | Layout |
|---|---|---|
| Módulo | `iMX6 Rex_V1I1.PrjPcb` | `iMX6 Rex_V1I1_PCB.PcbDoc` |
| Base | `iMX6 Rex Development Baseboard V1I1.PrjPcb` | `iMX6 Rex Development Baseboard V1I1_PCB.PcbDoc` |

Os projetos estão em `PCB_Avancado/Projetos/`, nas pastas `Modulo_L7-02` e `Placa_base_L7-01`. A [lista de materiais](PCB_Avancado/BoM/README.md) corresponde à configuração base, sem aplicação da variante **Prototype**.

## Referências

Projeto de referência **iMX6 Rex**, utilizado no **Advanced PCB Layout Course**, da **FEDEVEL Academy**.

- [iMX6 Rex](https://sites.google.com/imx6rex.com/www/home)
- [Development Baseboard](https://sites.google.com/imx6rex.com/www/application/imx6-development-board)
