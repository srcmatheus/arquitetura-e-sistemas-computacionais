# Sistemas Numéricos

Essencialmente, podemos definir um sistema numérico como um conjunto de regras e símbolos (algarismos) que representam quantidades de forma organizada, servindo para a realização de cálculos matemáticos.

Ao longo do tempo, diversos modelos de numeração foram adotados de acordo com a cultura ou necessidade das civilizações. Alguns exemplos notáveis são os sistemas Sumério, Romano, o vigesimal Maia e o formato mais difundido hoje em dia: o sistema decimal.

Na computação, três estruturas numéricas se destacam como as mais utilizadas no cenário atual:

| Sistema | Base | Dígitos | Aplicações |
| :------- | :--- | :------ | :--------- |
| Binário | 2 | 0 e 1 | Linguagem natural dos computadores, representando dados e instruções internas. |
| Decimal | 10 | 0 - 9 | Representação padrão de valores para humanos, utilizada em programação e interfaces de usuário. |
| Hexadecimal | 16 | 0 - 9, A - F | Representação compacta de códigos binários; mapeamento de memórias, cores Web e endereços IP/MAC. |

</br>

Existe também o sistema **octal (base 8)**, que foi amplamente empregado no passado devido à arquitetura dos computadores daquela época. Cada dígito octal correspondia a exatamente 3 bits ($2^3 = 8$), o que tornava esse modelo perfeito para agrupar dados. Com a evolução tecnológica, as palavras de dados passaram a ser múltiplas de 8 bits (bytes), tornando a utilização da base 8 obsoleta.

A computação utiliza a base binária porque seus componentes eletrônicos (transistores) operam apenas em dois estados distintos: ligado e desligado. Essa característica de dupla condição faz desse sistema a representação mais natural e direta para o hardware.

---

## Binário

O sistema binário é formado por apenas dois algarismos: 0 e 1. Trata-se de uma estrutura posicional de base 2 ($2^n$), empregada principalmente em circuitos digitais, onde esses dois valores representam estados físicos eletrônicos:
- 0 = Desligado (sem corrente elétrica / falso)
- 1 = Ligado (com corrente elétrica / verdadeiro)

Assim como o decimal, o binário é posicional, ou seja, o valor representado depende do posicionamento de cada dígito, definindo o seu peso em potências de 2.

Na computação, um dígito binário é chamado de bit. Uma sequência de 8 bits forma um byte. Com 8 bits, podemos obter 256 combinações diferentes (de 0 a 255).

> **Curiosidade**: O padrão de 8 bits = 1 byte foi consolidado pela IBM em 1964, no lançamento da família de computadores System/360. Como a empresa dominava o mercado na época, seu formato virou regra. Além disso, 8 bits são perfeitos para codificação de texto, permitindo criar $2^8 = 256$ combinações diferentes, o que possibilitou mapear todas as letras do alfabeto (originando a tabela ASCII expandida). Engenheiros de computação preferem tudo em potências de 2 ($2^3 = 8$) porque isso facilita o design dos circuitos, o endereçamento de memória e a divisão de dados em partes iguais (um byte de 8 bits pode ser dividido perfeitamente ao meio em dois *nibbles* de 4 bits).

### Decimal para binário

Para converter um número decimal para binário, devemos realizar divisões sucessivas pela base 2 até que o quociente seja zero. Os restos dessas divisões, lidos de trás para frente, formarão o código binário. Por exemplo, vamos converter o número 10:
- **10 ÷ 2 = 5 ⟶ resta 0**
- **5 ÷ 2 = 2 ⟶ resta 1**
- **2 ÷ 2 = 1 ⟶ resta 0**
- **1 ÷ 2 = 0 ⟶ resta 1**

Portanto, o número 10 em base decimal equivale a 1010 em binário.

### Binário para decimal

Neste caso, realizamos multiplicações sucessivas levando em consideração a base elevada à posição do dígito. Vamos converter $1010_2$ para a base dez:
- $(1 \times 2^3) + (0 \times 2^2) + (1 \times 2^1) + (0 \times 2^0) = 8 + 0 + 2 + 0 = 10$

---

Veja o esquema a seguir demonstrando o valor posicional de cada casa binária:

| Posição | Bit 7 | Bit 6 | Bit 5 | Bit 4 | Bit 3 | Bit 2 | Bit 1 | Bit 0 |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **Expoente** | $2^7$ | $2^6$ | $2^5$ | $2^4$ | $2^3$ | $2^2$ | $2^1$ | $2^0$ |
| **Valor (Decimal)** | **128** | **64** | **32** | **16** | **8** | **4** | **2** | **1** |

---

## Hexadecimal

É a base numérica que utiliza 16 símbolos (base 16). Sua principal funcionalidade atual é facilitar a leitura de códigos binários extensos. Um exemplo prático são os endereços de memória RAM, quase sempre representados nessa base, como `0x00FF4A`. Sua utilização também é padrão em códigos de cores na web e endereçamento de redes (como o IPv6).

O sistema hexadecimal combina os numerais decimais com as seis primeiras letras do alfabeto:
- 0 a 9 (possuem o mesmo valor do sistema decimal)
- A = 10
- B = 11
- C = 12
- D = 13
- E = 14
- F = 15

Convenientemente, o maior dígito hexadecimal (F, que vale 15) corresponde exatamente ao valor máximo que pode ser armazenado em 4 bits (binário `1111`). Isso significa que qualquer byte (8 bits) pode ser escrito com apenas dois dígitos hexadecimais.

### Binário para hexadecimal

A conversão é direta: como o valor máximo de um conjunto de 4 bits é 15, agrupamos o binário de quatro em quatro algarismos. Por exemplo:
- 1010 0101 (165 em decimal) = A5 (em hexadecimal).

> Caso o número binário não seja múltiplo de 4, preenchemos a sua esquerda com zeros até completarmos o bloco.

### Hexadecimal para decimal

Cada dígito possui um peso de acordo com sua posição, contada da direita para a esquerda, baseando-se em potências de 16:
- 1ª posição: vale $16^0 = 1$
- 2ª posição: vale $16^1 = 16$
- 3ª posição: vale $16^2 = 256$
- 4ª posição: vale $16^3 = 4096$

Para fazer a conversão, multiplica-se cada caractere pelo peso de sua respectiva posição e, no final, somam-se todos os resultados:

$$\text{Decimal} = (X \times 16^2) + (Y \times 16^1) + (Z \times 16^0)$$

Vamos converter o valor hexadecimal $3B2_{16}$ para decimal:
- Primeiro dígito: 2 na posição 0 ⟶ $2 \times 16^0 = 2$
- Segundo dígito: B (que equivale a 11) na posição 1 ⟶ $11 \times 16^1 = 176$
- Terceiro dígito: 3 na posição 2 ⟶ $3 \times 16^2 = 768$

Por fim, somando os resultados ($768 + 176 + 2$), obtemos $946$.

## Octal

Como mencionado, o sistema octal é raramente utilizado nos dias de hoje, mas vale o registro para fins didáticos.

Enquanto o sistema decimal usa 10 dígitos e o hexadecimal usa 16, o octal utiliza apenas 8 algarismos: 0, 1, 2, 3, 4, 5, 6 e 7.
Os pesos das posições seguem as potências de 8:
- 1ª posição: vale $8^0 = 1$
- 2ª posição: vale $8^1 = 8$
- 3ª posição: vale $8^2 = 64$
- 4ª posição: vale $8^3 = 512$

A conversão de octal para decimal segue a mesma lógica das bases anteriores. Veja o exemplo com $145_8$:
$$\text{Decimal} = (1 \times 8^2) + (4 \times 8^1) + (5 \times 8^0) = 101$$

Quando relacionado ao binário, cada dígito octal corresponde a exatamente 3 bits. Para realizar a conversão, basta segmentar o número binário em blocos de 3 bits (da direita para a esquerda) e substituir cada grupo pelo seu equivalente octal.

---