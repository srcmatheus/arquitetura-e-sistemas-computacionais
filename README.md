# Fundamentos de Sistemas de Computação

---

## Introdução

O objetivo deste repositório é organizar o conteúdo de fundamentos de sistemas de computação em um único local. A meu ver, dominar os pilares que sustentam toda a computação é crucial para uma carreira bem-sucedida. Sou apaixonado pelo assunto e não me contento com o superficial; busco compreender o funcionamento interno para então assimilar o todo, o que me traz profunda satisfação e confiança.

Embora o nível de detalhamento dependa da sua área de atuação, não sendo obrigatório decorar cada especificação técnica, conhecer os fundamentos é indispensável para embasar suas habilidades. Buscar um entendimento mais estrito é uma aspiração pessoal, mas ter clareza sobre os conceitos essenciais é importante para qualquer profissional.

Adquirir conhecimento transforma a mente, expande nossa visão de mundo e nos torna pessoas melhores.

---

## Estrutura do Conteúdo

Os tópicos abordados neste guia estão organizados de forma lógica e progressiva, partindo da abstração mais baixa (circuitos lógicos) até as camadas de software de sistema (sistemas operacionais).

### 1. Lógica Digital e Circuitos Combinacionais
* **Sistemas Numéricos:** Representação e conversão entre as bases binária, octal, decimal e hexadecimal.
* **Álgebra Booleana:** Teoremas, simplificação de expressões lógicas e mapeamento de circuitos.
* **Portas Lógicas e Tabelas-Verdade:** Blocos fundamentais de construção do hardware.
* **Circuitos Combinacionais Básicos:**
    * Meio-Somador (Half-Adder), Somador Completo (Full Adder) e Subtratores.
    * Codificadores e Decodificadores.
    * Multiplexadores (MUX) e Demultiplexadores (DEMUX).

### 2. Circuitos Sequenciais e Elementos de Memória
* **Circuitos Sequenciais:** Conceito de estado e a necessidade de sincronização.
* **Sinais de Controle:** Realimentação e o funcionamento do Clock.
* **Mecanismos de Armazenamento:**
    * Latch SR (Set-Reset) e Latch D (Transparent Latch).
    * Flip-Flops e sua aplicação em Registradores.
    * Estrutura interna da Memória RAM.

### 3. Arquitetura de Computadores e Execução
* **O Modelo de Von Neumann:** Unidade de Controle, Unidade Lógica e Aritmética (ULA), memória e barramentos.
* **O Processador (CPU):** Ciclo de busca, decodificação e execução de instruções.
* **Conjunto de Instruções (ISA):** A interface entre o hardware e o software.
* **Linguagem de Montagem (Assembly):** Programação em baixo nível e mapeamento direto para código de máquina.

### 4. Hierarquia e Gerenciamento de Memória
* **Hierarquia de Memória:** O balanço entre custo, capacidade e velocidade (Registradores, Cache, RAM e Armazenamento Secundário).
* **Memória Cache:** Princípios de localidade espacial e temporal.
* **Endereçamento Físico:** Mapeamento de memória e impacto da largura do barramento.
* **Manipulação de Memória em Baixo Nível:**
    * Ponteiros e Aritmética de Ponteiros.
    * Segmentação de Memória: Stack (Pilha) e Heap (Monte).
    * Mecanismos de Gerenciamento: Alocação manual vs. Coleta de lixo (Garbage Collector).
* **Segurança e Estruturas:** Conceito de Buffer e vulnerabilidades de Estouro de Buffer (Buffer Overflow).

### 5. Sistemas Operacionais e Abstrações de Software
* **O Kernel:** O núcleo do sistema operacional e o gerenciamento de recursos de hardware.
* **Chamadas de Sistema (Syscalls):** A ponte de comunicação entre o espaço do usuário e o espaço do kernel.
* **Concorrência:** Diferenças entre Processos e Threads, e o custo da Troca de Contexto (Context Switching).
* **Memória Virtual:** O conceito de paginação, tabelas de página e isolamento de processos.

---

## Como Utilizar Este Guia

Este repositório foi desenhado para ser lido de forma sequencial ou consultado por tópicos específicos. Cada seção principal possui anotações teóricas seguidas, quando aplicável, de exemplos práticos ou diagramas explicativos.