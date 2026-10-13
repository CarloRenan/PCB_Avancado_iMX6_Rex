# Lista de materiais — BOM

[Abrir a planilha BOM_e_Cotacao.xlsx](BOM_e_Cotacao.xlsx).

As quantidades são **por uma placa**, para o projeto base **sem aplicar a variante Prototype**. Os códigos de fabricante, fabricantes, valores e descrições vêm dos esquemáticos originais; o footprint vem do PCB. Não foram pesquisados preços atuais de componentes nem inventados códigos LCSC.

| Lista | Componentes com MPN | Grupos na BOM | Objetos no inventário completo |
|---|---:|---:|---:|
| Módulo | 457 | 66 | 473 |
| Placa base | 546 | 124 | 580 |

Arquivos `*_BOM.csv` agrupam componentes com o mesmo valor, MPN, fabricante, footprint e descrição. Os designadores identificam cada posição. Um componente dividido em vários símbolos, como U1 do módulo, é contado apenas uma vez por placa.

Arquivos `*_Inventario_PCB.csv` registram **todos** os objetos de componente, incluindo furos, fiduciais, pontos de teste e representações mecânicas. A tabela `Itens_auxiliares.csv` e a aba correspondente também mantêm os itens que aparecem apenas no esquemático, como bateria, jumpers, referência à PCB e referência ao firmware. Esses itens precisam ser avaliados separadamente para compra e montagem; a referência ao firmware não significa que seu binário esteja incluído.

## Variante de montagem

Os projetos possuem uma variante denominada **Prototype**, com 29 registros de alteração no módulo e 76 na base. Os arquivos `*_Variantes_originais.csv` preservam designador, código `Kind` e demais identificadores como aparecem nos `.PrjPcb`.

Essas alterações **não foram aplicadas** às BOMs aqui produzidas. Abra **Project → Variants** no Altium, confirme o estado de montagem de cada componente e exporte a BOM da variante escolhida antes de encomendar. Uma variante pode manter o footprint no PCB e retirar um componente da BOM quando ele é marcado como não montado; por isso o inventário de footprints não deve ser usado sozinho como lista final de compra. [Referência Altium](https://www.altium.com/pt/documentation/altium-designer/design-variants).

## Conferência da extração

- 473/473 objetos do módulo e 580/580 da base associados aos respectivos designadores nos esquemáticos.
- Nenhum designador repetido em cada PCB.
- Parâmetros de compra comparados entre símbolos multipartes, sem divergências nos campos utilizados.
- Fabricante e MPN alternativos em `Manufacturer 1` / `Manufacturer Part Number 1` considerados quando presentes, como em J3 da base.
- Preços e estoques antigos gravados nas bibliotecas não foram utilizados como cotação atual.

Esta BOM documenta o material recebido e precisa da revisão de variante e da compatibilização com o catálogo da montadora para uso em produção.
