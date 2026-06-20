# Álgebra Booleana

Antes de mais nada, álgebra é um ramo da matemática que utiliza símbolos e letras para representar números e expressar relações entre eles.

A álgebra booleana é uma variante da álgebra comum, desenvolvida por George Boole in 1854. O objetivo deste trabalho na época era estabelecer a lógica como uma ciência matemática utilizando operações simples. Cerca de 100 anos mais tarde, esse trabalho se tornou fundamental para a construção e programação de computadores eletrônicos.

Na álgebra booleana, variáveis podem assumir dois valores: 0 (falso/baixo) ou 1 (verdadeiro/alto). Além disso, existem 3 operadores fundamentais: **AND**, **OR** e **NOT** (E, Ou e Não). Estas três funções são as únicas operações necessárias para efetuar comparações ou as quatro operações aritméticas base. Vejamos mais detalhadamente cada uma:
- **AND**: o resultado é 1 se todas as entradas forem 1. É representada por um ponto ($A \cdot B$) ou apenas juntas ($AB$).
- **OR**: o resultado é 1 se pelo menos uma das entradas for 1. É representada pelo sinal de mais ($A + B$).
- **NOT**: inverte o sinal de entrada. É representada por uma barra sobre a variável ($\bar{A}$) ou por um apóstrofo ($A'$).

Existem teoremas que servem como "leis da física" do universo binário. São como regras para manipular equações e representações equivalentes.

Como dito antes, a álgebra booleana possui 2 variáveis: 0 e 1. Os teoremas ditam as regras para o que acontece quando esses valores se cruzam.

## Identidade, anulação e idempotência

- **Identidade $(A + 0 = A)$**: A pode receber o valor de 0 ou 1, enquanto 0 é um valor fixo da equação. Uma porta **OR** funciona se pelo menos uma das entradas for 1. Como uma das entradas está fixada em 0, o resultado depende exclusivamente de A.

- **Anulação ($A + 1 = 1$)**: nesse caso temos uma entrada fixa em 1. Em uma porta **OR**, não importa o valor de A, o resultado sempre será 1, já que o circuito foi "travado" em 1.

- **Idempotência ($A \cdot A = A$ e $A + A = A$)**: Em circuitos, se você pega o mesmo fio $A$ e liga nas duas entradas de uma porta AND ($\cdot$) ou OR ($+$), você não está criando uma informação nova. Se o fio traz 1, o resultado é 1. Se traz 0, o resultado é 0. É redundante.

## Teoremas de De Morgan

São as duas leis mais importantes da Álgebra Booleana, que mostram como negar uma operação conjunta. Servem para provar que você pode transformar uma porta **OR** em uma porta **AND** e vice-versa, desde que inverta os sinais das entradas e saídas.

### Primeiro Teorema (Negação de soma)
O primeiro teorema afirma que o complemento (a negação) de uma soma lógica (OR) é igual ao produto (AND) dos complementos das variáveis isoladas.

$$\overline{A + B} = \bar{A} \cdot \bar{B}$$

### Segundo teorema (Negação do produto)
O segundo teorema afirma que o complemento (a negação) de um produto lógico (AND) é igual à soma (OR) dos complementos das variáveis isoladas.

$$\overline{A \cdot B} = \bar{A} + \bar{B}$$

---

A negação total de ambas as portas (OR e AND) é conhecida como NOR e NAND. Veja a tabela abaixo:

| Porta | Operação (Negação total) | Equivalente (Negação individual) | Resultado |
| --- | --- | --- | --- |
| OR | $A + B$ | — | É $1$ se pelo menos uma entrada for $1$ |
| AND | $A \cdot B$ | — | Só é $1$ se ambas as entradas forem $1$ |
| NOR | $\overline{A + B}$ | $\bar{A} \cdot \bar{B}$ | Só é $1$ se todas as entradas forem $0$ |
| NAND | $\overline{A \cdot B}$ | $\bar{A} + \bar{B}$ | Só é $0$ se ambas forem $1$ |

> Pode parecer que a negação total é igual à negação individual, mas não, pois na negação total, o resultado final é invertido e na individual, são as variáveis que são invertidas.

---

## Simplificação de expressões lógicas

Em hardware, cada operação lógica (AND, OR, NOT) se transforma em um grupo de transistores físicos dentro de um chip.
Se você tem uma expressão lógica gigante e não a simplifica, o seu chip final terá:
- Mais consumo de energia (mais transistores dissipando calor).
- Maior latência/atraso (a eletricidade demora mais para viajar por tantas portas).
- Maior custo de fabricação (chips maiores e mais complexos).

Simplificar serve para otimizar eficiência, velocidade e custo.

---

## Mapeamento de circuitos

O mapeamento é a tradução da matemática abstrata para a engenharia física. Ele pega a equação simplificada e gera o diagrama de portas lógicas (o circuito). Esse diagrama é o que os engenheiros usam para desenhar as trilhas de cobre em uma placa de circuito impresso (PCB) ou as conexões de silício em um processador.