## Hierarquia de Memória

A velocidade de processamento das CPUs evoluiu muito mais rapidamente que a velocidade de acesso às memórias. Ou seja, se um processador buscasse cada instrução diretamente na memória RAM, ele passaria a maior parte do seu tempo ocioso, aguardando a chegada dos sinais elétricos.

Para resolver esse problema de espera do processador, os engenheiros estruturaram múltiplos níveis de memória, com o objetivo de criar uma "ilusão" para o processador de que seu espaço de trabalho é infinito. A solução foi integrar memórias extremamente rápidas diretamente dentro da CPU, criando uma hierarquia de memória que vai desde a mais rápida até a mais lenta. O objetivo dessas memórias é armazenar as instruções e os dados mais recorrentes, para que o processador não perca ciclos de processamento tendo que buscá-los novamente na memória RAM.

Este é exatamente o Gargalo de Von Neumann. Não existe uma tecnologia única que entregue alto desempenho e alta capacidade de forma simultânea e viável. Cada nível do sistema utiliza uma arquitetura eletrônica diferente para cumprir seu papel na base de execução:

### Registradores

Possuem o mais absoluto desempenho, porém, são as estruturas mais caras de toda a máquina. Residem internamente nos núcleos do processador e são constituídos pela mesma lógica rápida (flip-flops de estado sólido) que processa as operações matemáticas, operando diretamente na frequência da CPU. Seu objetivo é armazenar os operandos imediatos e as variáveis exatas mais utilizadas pela CPU naquele instante.

Em um processador moderno de 64 bits, a grande maioria dos registradores tem a largura de 64 bits (ou seja, apenas 8 bytes cada). Além disso, a quantidade total de registradores dentro de uma CPU é bem pequena, normalmente variando entre 16 e algumas dezenas de registradores de propósito geral, dependendo da arquitetura (como x86-64 ou ARM).

### Memória Cache

É uma memória incorporada ao molde do próprio processador, construída com tecnologia SRAM (*Static Random Access Memory*).

> Diferentemente da memória RAM comum, onde os capacitores precisam ser "recarregados" o tempo todo (DRAM), a SRAM utiliza *latches* ou *flip-flops*, formados por múltiplos transistores. Enquanto o computador estiver energizado, os dados ficam guardados sem precisar de ciclos de atualização. Dessa forma, não há perda de tempo com a recarga dos capacitores, tornando a resposta quase instantânea.

A cache é dividida em níveis que equilibram velocidade e capacidade:

- **Cache L1 (Nível 1):**
  - É a menor e mais rápida de todas, ficando embutida diretamente dentro de cada núcleo do processador.
  - Guarda as instruções e os dados mais críticos que a CPU vai usar imediatamente.
  - Geralmente varia de 64 KB a 512 KB por núcleo.

- **Cache L2 (Nível 2):**
  - Um pouco maior e sutilmente mais lenta que a L1, mas ainda ultrarrápida.
  - Geralmente dedicada a cada núcleo ou compartilhada de forma muito próxima.
  - Costuma ter de 512 KB a 2 MB ou 4 MB por núcleo.

- **Cache L3 (Nível 3):**
  - A maior das caches, compartilhada entre todos os núcleos da CPU.
  - É mais lenta que a L1 e a L2, mas ainda é significativamente mais rápida do que buscar os dados na memória RAM.
  - Seu tamanho varia bastante atualmente, podendo ir de 16 MB até quase 100 MB (ou mais, em processadores topo de linha e voltados para jogos, que utilizam empilhamento 3D).

### Memória Principal (RAM)

A memória RAM é o maior espaço de trabalho do processador, equilibrando velocidade e capacidade de armazenamento a um custo acessível. A sigla RAM significa *Random Access Memory* (Memória de Acesso Aleatório). O termo "aleatório" significa que o processador pode ler ou gravar dados em qualquer posição da memória instantaneamente, sem precisar acessá-los em ordem sequencial (diferentemente de uma fita magnética ou de um disco rígido antigo, por exemplo).

A RAM é o principal componente de armazenamento de curto prazo: o sistema operacional e todos os outros programas abertos no computador ficam alocados nela. Então, sempre que um programa é executado no computador, ele primeiro é carregado na memória RAM para que a CPU consiga interagir com esses dados rapidamente.

Diferentemente da memória cache (que utiliza tecnologia SRAM), a memória RAM comum (DRAM) utiliza capacitores minúsculos combinados com transistores para armazenar cada bit. Como os capacitores perdem carga elétrica naturalmente com o tempo, eles precisam ser recarregados milhares de vezes por segundo (*refresh*). Esse processo, somado à distância física entre o processador e os pentes de RAM, cria um atraso perceptível se comparado à velocidade instantânea da SRAM.

Outra característica das memórias RAM é a volatilidade, ou seja, quando o computador é desligado ou a energia é cortada, tudo o que estava armazenado desaparece completamente. Por isso, é necessário salvar os dados de forma persistente em SSDs ou HDs.

Como dito anteriormente, a memória RAM é o ponto de equilíbrio entre velocidade e capacidade de armazenamento. E, diferentemente da memória cache, a RAM vem em módulos que são encaixados nos *slots* da placa-mãe e podem ser substituídos ou expandidos facilmente.

### Armazenamento Secundário (Memória Não Volátil)

Ao contrário da RAM, que perde seus dados quando a energia é cortada, as memórias secundárias armazenam os dados de forma persistente, mesmo na ausência de energia, até que você decida apagá-los. Em termos práticos, significa que a informação é gravada de forma persistente.

Atualmente, temos dois tipos principais de armazenamento secundário no mercado; vamos falar sobre cada um deles:

- **HD (*Hard Disk* ou Disco Rígido):** É uma tecnologia mecânica mais antiga que utiliza discos magnéticos giratórios e uma agulha física que lê e grava os dados nos pratos. Seu custo por gigabyte é bem baixo e geralmente oferece um grande espaço de armazenamento; porém, sua maior desvantagem é a extrema lentidão nos tempos de acesso.
- **SSD (*Solid State Drive* ou Unidade de Estado Sólido):** É composto por chips de memória *flash* baseados em silício (NAND), sem nenhum componente mecânico. Sua velocidade é absurdamente maior se comparada à do HD, além de ser silencioso, leve e mais resistente a impactos. Geralmente, tem um custo por gigabyte um pouco mais alto que um HD convencional.

De maneira resumida, HDs e SSDs são unidades de armazenamento utilizadas para manter os dados a longo prazo, ou seja, para guardar permanentemente programas, vídeos, fotos e qualquer outro tipo de arquivo. Atualmente, a escala de capacidade dessas memórias costuma ficar na casa dos gigabytes (GB) e terabytes (TB), viabilizando o armazenamento de grandes volumes de dados.