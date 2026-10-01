## Realimentação
É um mecanismo fundamental que transforma um circuito combinacional (apenas entradas atuais) em um elemento de memória. Por exemplo, quando a saída de uma porta lógica é direcionada de volta para a entrada do mesmo circuito, é literalmente uma realimentação.

Esse laço fechado cria um estado estável onde o circuito consegue “lembrar” a informação anterior, sendo esta uma forma de armazenar o resultado anterior para que ele possa ser reutilizado na próxima operação.

## Funcionamento do Clock
O sinal de clock é uma onda quadrada periódica que funciona como um “metrônomo” de um sistema digital síncrono. Ele é responsável por coordenar o exato momento em que todos os blocos de memória devem atualizar seus dados.

Em circuitos combinatórios puros, as portas lógicas levam um tempo mínimo, conhecido como atraso de propagação, para que as entradas sejam processadas e refletidas na saída. O problema é que, devido aos atrasos físicos dos fios e portas lógicas, os sinais podem chegar em momentos diferentes, gerando pulsos indesejados, conhecidos como *glitches*. Essa situação faria o circuito entrar em um estado caótico e imprevisível, oscilando incontrolavelmente.

Então o clock surge para resolver este problema, estabelecendo uma regra em que todos os estados mudam ao mesmo tempo, de acordo com o ritmo ditado pelo clock. Em outras palavras, o clock é como um pulso que avisa que todos os circuitos podem mudar de estado ao mesmo tempo.

Fisicamente, o clock oscila entre duas tensões fixas estipuladas pela tecnologia do circuito. Geralmente são divididos em:
- **Nível baixo (0V / Falso):** Representa a ausência de tensão (ou nível de referência). Durante o período em que o clock está em nível baixo, as portas lógicas de controle internas do elemento de memória bloqueiam a entrada de novos dados.
- **Nível Alto (5V/3.3V / Verdadeiro):** Representa a tensão de alimentação ativa. Quando o clock sobe para o nível alto, ele fornece o potencial elétrico necessário para polarizar os transistores internos de forma que eles permitam a passagem ou a captura do sinal de dados.

O componente responsável pelo clock, na maioria dos dispositivos, é um cristal de quartzo. A física desse cristal e o circuito eletrônico de temporização determinam autonomamente o ritmo, a duração e a alternância do clock, ditando a batida que o sistema inteiro é obrigado a seguir. Além disso, quem dita essas especificações do clock é o projeto do hardware, que dita absolutamente tudo sobre como esse clock vai ser distribuído, tratado e aproveitado dentro do sistema.

Há um detalhe importante em que elementos de memória (como *latches* e *flip-flops*) reagem ao clock de duas formas diferentes:
- **Sensível a Nível (*Level-Triggered Latches*):** O elemento de memória aceita novos dados durante todo o tempo em que o clock estiver em um nível específico (por exemplo, no Nível Alto). É como uma catraca liberada: enquanto o sinal estiver alto, qualquer dado pode passar e alterar a saída.
- **Sensível a Borda (*Edge-Triggered Flip-Flops*):** O elemento só captura os dados no exato instante em que o clock muda de estado (seja subindo de 0V para 5V, ou descendo de 5V para 0V). É como tirar uma fotografia: o dado só é registrado naquele milissegundo do "clique", ignorando o que acontece antes ou depois.

## Sistemas Síncronos vs. Assíncronos
- **Circuitos Assíncronos:** Mudam de estado imediatamente quando as entradas mudam, dependendo apenas da velocidade de propagação dos componentes e da realimentação. São mais rápidos, mas complexos e propensos a erros de temporização.
- **Circuitos Síncronos:** Utilizam o sinal de clock para ditar o ritmo. As mudanças de estado ocorrem de forma ordenada e previsível, facilitando o projeto de sistemas complexos.