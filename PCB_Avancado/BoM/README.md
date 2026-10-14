# Lista de materiais

[Abrir a planilha BOM_e_Cotacao.xlsx](BOM_e_Cotacao.xlsx)

A BOM apresenta os componentes eletrônicos do módulo iMX6 Rex e da Development Baseboard. As quantidades correspondem a **uma unidade de cada placa**, na **configuração base, sem aplicação da variante Prototype**.

| Placa | Componentes com MPN | Grupos na BOM | Objetos no inventário PCB |
|---|---:|---:|---:|
| Módulo | 457 | 66 | 473 |
| Placa base | 546 | 124 | 580 |

## Campos da BOM

| Campo | Descrição |
|---|---|
| Designador | Identificação do componente no esquemático e na PCB |
| Quantidade | Número de componentes por placa |
| Valor | Valor nominal ou identificação funcional |
| MPN | Código do componente no catálogo do fabricante |
| Fabricante | Fabricante do componente |
| Footprint | Padrão de montagem na PCB |
| Descrição | Características do componente |

Componentes com o mesmo valor, MPN, fabricante, footprint e descrição são agrupados na mesma linha. Os designadores identificam cada posição de montagem. Componentes com símbolos multipartes, como o processador U1, correspondem a uma única peça física.

## Conteúdo dos arquivos

| Arquivo | Conteúdo |
|---|---|
| `BOM_e_Cotacao.xlsx` | Listas de materiais, itens auxiliares e orçamento JLCPCB |
| `*_BOM.csv` | Componentes agrupados por especificação |
| `*_Inventario_PCB.csv` | Inventário de componentes, elementos mecânicos, fiduciais e pontos de teste |
| `Itens_auxiliares.csv` | Elementos auxiliares e referências complementares dos esquemáticos |
| `*_Variantes_originais.csv` | Registros de configuração da variante Prototype |

Os códigos de fabricante, valores e descrições estão associados aos esquemáticos. Os footprints correspondem aos documentos PCB. A lista de itens auxiliares inclui elementos como furos de fixação, fiduciais, pontos de teste, bateria, jumpers e referências à PCB e ao firmware.

## Configuração de montagem

A variante **Prototype** contém 29 registros de configuração no módulo e 76 na placa base. Ela é definida separadamente da configuração base utilizada nesta BOM. Os arquivos de variantes relacionam os designadores aos respectivos códigos de configuração dos projetos Altium.

[Documentação de variantes no Altium Designer](https://www.altium.com/pt/documentation/altium-designer/design-variants).
