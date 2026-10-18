## Conjunto de Instruções (ISA)

Para que o hardware e o software possam se comunicar, é necessário um conjunto de instruções que atue como um contrato irrevogável entre o hardware físico e o software (como o sistema operacional, por exemplo). É então que surge a ISA (*Instruction Set Architecture*), ou Arquitetura do Conjunto de Instruções.

Para o software, a ISA define exatamente o que o processador é capaz de fazer. Para o hardware, a ISA define o que os circuitos devem ser capazes de suportar e executar. Uma analogia técnica precisa é considerar a ISA como a API (*Application Programming Interface*) em nível de máquina: se o código-fonte compila para respeitar essa "API" (como o `x86-64` ou `ARMv8`), o processador garantirá a execução correta, independentemente de como seus circuitos internos (microarquitetura) foram projetados.

A ISA expõe regras rígidas para o desenvolvedor de baixo nível. É importante ressaltar que cada fabricante documenta sua ISA de acordo com suas especificidades de projeto. Existem elementos fundamentais ditados pela ISA para orientar o desenvolvimento de compiladores. Veja:

- **O Banco de Registradores Visíveis:** Define quantos registradores de uso geral estão disponíveis, seus tamanhos (ex.: 32 bits, 64 bits) e seus nomes lógicos (como `RAX` no x86 ou `X0` no ARM). Também define registradores de controle e status, como o `PC` (*Program Counter*) e o registrador de `FLAGS`.
- **Tipos de Dados Nativos:** Estabelece os formatos que o hardware compreende nativamente, como inteiros com ou sem sinal (de 8, 16, 32 ou 64 bits), números em ponto flutuante (padrão IEEE 754) e caracteres.
- **Modelo e Organização de Memória:** Determina como os endereços de memória são calculados e gerenciados. Define se a memória é endereçada por byte (*byte-addressable*), como ocorre o alinhamento de memória e qual é a ordem de armazenamento dos bytes (*Endianness*: *Little-Endian* ou *Big-Endian*).
- **O Repertório de Instruções:** A lista taxativa de todos os comandos que a CPU consegue decodificar e executar.
- **Modos de Endereçamento:** As diferentes formas como uma instrução pode localizar e acessar os dados de que precisa (seus operandos).

No nível mais fundamental, uma instrução é apenas uma sequência de bits lida da memória. A ISA dita o formato (*Instruction Format*) de como o hardware deve fatiar e interpretar esses bits durante a fase de Decodificação. Toda instrução é dividida basicamente em:

- **Opcode (*Operation Code*):** O campo binário central que identifica a ação a ser realizada (ex.: `0010` para SOMA, `0100` para SALTO).
- **Operandos:** Os argumentos da instrução. Dependendo do *opcode*, a instrução pode ter zero operandos (ex.: `NOP`, *No Operation*), um, dois ou até três operandos, que representam dados de origem e destinos para os resultados.

Portanto, a Arquitetura do Conjunto de Instruções (ISA) funciona como um contrato formal e padronizado entre o software e o hardware, definindo o vocabulário básico de comandos binários, registradores, tipos de dados e modos de endereçamento que um processador é capaz de compreender. Enquanto o desenvolvedor escreve em linguagens de alto nível sem precisar conhecer os circuitos físicos, o compilador traduz essa lógica para a ISA específica da máquina de destino, gerando o código de máquina correspondente. Por sua vez, a engenharia de hardware projeta os transistores, decodificadores e unidades funcionais para responder com precisão a cada uma dessas instruções, garantindo que o programa execute de maneira consistente e compatível, independentemente de mudanças ou avanços na microarquitetura interna do chip.