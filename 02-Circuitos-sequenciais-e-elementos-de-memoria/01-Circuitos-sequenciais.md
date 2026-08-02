## Conceito de estado e sincronização

Circuitos combinacionais (como o Full-Adder, por exemplo) têm suas saídas determinadas unicamente por suas entradas no exato instante atual. Eles não possuem “memória” e, por isso, não armazenam operações anteriores.

No entanto, para que seja possível construir sistemas computacionais mais complexos, é necessário que os circuitos possam armazenar estados passados, de modo a tomar decisões baseadas nesses resultados. Para resolver esse problema, surgem então os circuitos sequenciais.

### Conceito de “Estado”

Antes de entendermos os circuitos digitais sequenciais, precisamos entender o que são seus estados.

De maneira simples, o estado de um circuito digital é o conjunto de informações armazenadas que resume todo o histórico de entradas passadas necessário para determinar o comportamento futuro do sistema.

O estado atual ($Q$) representa a “memória” do circuito no tempo ($t$). A saída ($Y$) e o próximo estado ($Q_{próximo}$) dependem da entrada atual ($X$) e do estado atual ($Q$).

$$Q_{próximo} = Q(t+1) = f(X(t), Q(t))$$

$$\text{Saída } Y(t) = g(X(t), Q(t))$$

Essa capacidade de “memória” é obtida por meio da realimentação (*feedback*), que ocorre quando a saída de um circuito é conectada de volta à sua entrada, seja diretamente ou através de elementos de atraso. A principal função da realimentação é armazenar informações (estado); sem ela, seria impossível construir computadores modernos, já que os circuitos não “lembrariam” de cálculos anteriores.

Para que fique claro, vamos exemplificar esse funcionamento através de um somador série:

Em um sistema com um único Full-Adder, o valor de uma soma é calculado coluna por coluna usando o mesmo circuito repetidamente.

Vamos usar como exemplo a soma dos seguintes valores binários:

$$0011_2 \text{ (3)} + 0101_2 \text{ (5)}$$

A soma da primeira coluna gera um *carry* (vai-um), que vai para o circuito de realimentação, sendo inserido na operação seguinte para realizar a soma da próxima coluna. O resultado final vai sendo deslocado e armazenado em um registrador de deslocamento (*shift register*).

Existem também os somadores paralelos, onde cada coluna de bits é somada por um circuito físico dedicado ao mesmo tempo. Neles, o *carry* flui diretamente de um bloco combinacional para o outro, mas os resultados finais da soma ainda precisam ser capturados por registradores para que a CPU possa utilizá-los no ciclo seguinte.

### Variáveis de estado

É o conjunto de variáveis (geralmente as saídas dos elementos de memória armazenados em *latches* e *flip-flops*) cujos valores determinam completamente o comportamento de um sistema em qualquer momento futuro.

Por exemplo, em um videogame, quando você pausa o jogo, as variáveis de estado são os dados salvos no arquivo (posição do personagem, vida restante, fase atual). Com esses dados, é possível recriar exatamente a situação do jogo a partir daquele ponto.

### Espaço de estado

É um espaço vetorial multidimensional onde cada eixo coordenado representa uma variável de estado do sistema. Se um circuito possui $N$ variáveis de estado, o espaço de estado terá $N$ dimensões. Cada ponto específico nesse espaço representa uma configuração única.

Por exemplo, imagine um circuito com dois *flip-flops* ($Q_1$ e $Q_2$). As combinações possíveis de estados são $00$, $01$, $10$ e $11$. Ou seja, o espaço de estado possui 2 dimensões e existem 4 pontos de estado possíveis nesse espaço. Conforme o sinal de *clock* avança e as entradas mudam, o circuito "salta" de um ponto para outro nesse espaço (transição de estados).

Retornando ao exemplo anterior com o circuito do Full-Adder em um somador série, pense na variável de estado como o *carry*, que é o dado que precisa ser registrado para a operação futura, exatamente o bit guardado no *flip-flop* de realimentação. Em relação ao espaço de estado, como temos apenas 1 bit de estado (*carry* pode ser 0 ou 1), o espaço de estado tem apenas 1 dimensão e 2 pontos possíveis.

### Sincronização

A sincronização é o processo que coordena os dados para garantir que cheguem aos destinos corretos nos momentos exatos, sem corromper a informação. Se não houvesse um mecanismo de controle temporal, o sistema não saberia quando ler determinado dado e as informações poderiam se misturar, gerando erros graves. A sincronização garante a previsibilidade, a confiabilidade e a organização do fluxo de dados.

Fisicamente, a sincronização é realizada por circuitos sequenciais temporizados, sendo o exemplo mais clássico e fundamental o *Flip-Flop* tipo D (D-Flip-Flop) operando como um elemento de captura sincronizado.

Em um sistema puramente assíncrono, o estado do circuito muda imediatamente no momento em que qualquer entrada varia ou assim que o sinal se propaga pelas portas lógicas. Isso gera sérios problemas, como atrasos de propagação desalinhados e mudanças indevidas de sinais.

Para evitar o caos dos tempos de propagação diferentes, introduz-se um sinal maestro: o *Clock* (relógio do sistema). O sinal de *clock* é uma onda quadrada periódica que dita exatamente quando todos os elementos de memória do circuito têm permissão para ler o próximo estado e atualizar o seu valor.

Em resumo, enquanto os circuitos combinacionais realizam o trabalho imediato de processamento, são os circuitos sequenciais que dão estrutura e estabilidade aos sistemas digitais. A união da capacidade de cálculo com a retenção de **estado** permite que computadores executem rotinas complexas passo a passo.

Por fim, a **sincronização** via *clock* atua como o maestro indispensável dessa arquitetura: ela garante que o estado do sistema só mude quando todos os cálculos intermediários estiverem devidamente estabilizados, evitando erros e tornando o fluxo de dados totalmente previsível.