# Galeria — layout e vistas 3D

As imagens documentam os arquivos finais disponíveis no curso: módulo **L7-02** e placa base **L7-01**. Clique em uma imagem para abri-la em maior tamanho.

## Conjunto montado

![Vista mecânica do conjunto](Conjunto_3D.png)

O módulo desta vista é o corpo STEP **M1**, incorporado ao projeto da placa base. Ele mostra a montagem mecânica de referência. Para examinar especificamente o módulo da aula L7-02, use suas vistas individuais abaixo.

## Módulo iMX6 Rex — L7-02

| Face superior | Face inferior, vista por baixo |
|---|---|
| ![Módulo — face superior](Modulo_3D_superior.png) | ![Módulo — face inferior](Modulo_3D_inferior.png) |

70 × 40 mm · 12 camadas de cobre · processador, DDR3, flash e PHY Ethernet.

## Development Baseboard — L7-01

| Face superior, sem o módulo | Face inferior, vista por baixo |
|---|---|
| ![Base — face superior](Placa_base_3D_superior.png) | ![Base — face inferior](Placa_base_3D_inferior.png) |

135 × 110 mm · 6 camadas de cobre · alimentação e interfaces externas.

## Layouts 2D

![Comparação das quatro faces](PCB_Avancado_Layouts.png)

| Placa | Face superior | Face inferior |
|---|---|---|
| Módulo | [Abrir PNG](Modulo_Superior.png) | [Abrir PNG](Modulo_Inferior.png) |
| Base | [Abrir PNG](Placa_base_Superior.png) | [Abrir PNG](Placa_base_Inferior.png) |

## Origem e alcance das imagens

As vistas 3D foram reconstruídas usando os **modelos STEP e corpos extrudados incorporados aos próprios arquivos Altium**, com os posicionamentos e rotações registrados no PCB. Os modelos foram convertidos em malhas com OpenCascade e renderizados para PNG. São visualizações do projeto, não fotografias de placas fabricadas ou capturas do visualizador do Altium.

As vistas individuais representam 457 referências de componente no módulo e 546 na base. Objetos auxiliares, pontos de teste e itens sem volume podem aparecer apenas como pads. Os modelos de cartões de expansão CR1/CR2 foram omitidos para deixar os conectores visíveis. M1 aparece somente na vista do conjunto.

Contornos e furos de fixação vêm da geometria do PCB. A espessura visual foi definida em **1,6 mm**, conforme a cotação fornecida; não equivale à validação do empilhamento do projeto. Cores, materiais, detalhes de furação, cobre, vias e serigrafia estão simplificados. A variante Prototype não foi aplicada às imagens.

As prévias 2D usam as coordenadas do PCB e mostram trilhas externas, pads, vias e contornos. Não exibem todos os planos nem todas as camadas. As placas não estão na mesma escala nas comparações.

Para inspecionar todas as camadas ou validar encaixes e fabricação, abra os [arquivos originais](../Projetos/) no Altium Designer.
