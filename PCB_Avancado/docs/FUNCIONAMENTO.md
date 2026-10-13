# Funcionamento do conjunto

O iMX6 Rex separa o núcleo de processamento da placa que conecta periféricos. Essa arquitetura permite manter o mesmo módulo e adaptar a placa base à aplicação.

## Módulo

| Bloco | Componentes identificados no projeto | Papel |
|---|---|---|
| Processamento | U1 — MCIMX6Q5EYM10AC | Executar software embarcado e controlar interfaces |
| Memória de trabalho | U2–U5 — MT41J128M16HA-15E:D TR | Memória DDR3 utilizada durante a execução |
| Memória não volátil | U10 — SST25VF016B-75-4I-QAF | Flash SPI; o esquemático contém uma referência a uBoot |
| Ethernet | U8 — KSZ9021RN | Interface física Ethernet |
| Ligação com a base | J1 e J2 — QSH-030-01-L-D-A | Transportar alimentação e sinais entre as placas |

Os parâmetros de U1 no esquemático identificam um ARM Cortex-A9 de 32 bits, quatro núcleos e 1,0 GHz. Esses são dados do componente escolhido no projeto, não resultado de uma medição de desempenho desta entrega.

## Placa base

A base usa os conectores correspondentes QTH-030-01-L-D-A para receber o módulo. Seus esquemáticos organizam as funções em folhas dedicadas a PCIe, SATA/CFast, HDMI, LVDS, USB, Ethernet, áudio, SD, UART, RTC/EEPROM, GPIO e alimentação.

Na prática, ela oferece os caminhos elétricos e conectores para desenvolver um equipamento com tela, rede, armazenamento e periféricos. O projeto de referência descreve dois encaixes mini PCIe com funções diferentes: um oferece PCIe/USB/SIM e o outro USB/SIM/voz; não são duas portas PCIe equivalentes. [Documentação da base](https://sites.google.com/imx6rex.com/www/application/imx6-development-board).

## O que o curso exercita

Os dois layouts permitem estudar roteamento de interfaces rápidas, organização de camadas, distribuição de alimentação e regras de impedância. A última atividade encontrada para o módulo é o ajuste de impedância; para a base, o ajuste fino dos pares diferenciais.

O repositório reúne arquivos de hardware. Firmware executável, sistema operacional, testes de bancada e validação elétrica das placas não fazem parte do material final disponível aqui.
