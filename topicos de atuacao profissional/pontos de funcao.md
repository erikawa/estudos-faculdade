# Análise de Pontos de Função

Método padrão para medir o software através da qualificação da funcionalidade fornecida ao usuário.

## Objetivo

* Media a funcionalidade que o usuário solicite;
* Medir o desenvolvimento e manutenção do software de forma independente da tecnologia utilizada para sua implementação;
* Prover padrão de medida, simples e consistente através de diversos protocolos;

## Aplicabilidade

* Medir o tamanho de um pacote através da contagem das funções incluidas;
* Suportar a análise de produtividade e qualidade;
* Meio de estimar custo e recurso para o desenvolvimento e manutenção do software;
* Como fator de normalização para comparação de software;

## Visão do usuário

* Descrição formal das regras de negócio;
* Aprovado pelo usuário;
* Pode variar na forma física;

## Características

* É realizado utilizando uma terminologia comum a ambos usuário e desenvolvedores;
* Independe da linguagem e do ambiente que a aplicação será desenvolvida;
* É aplicavel ao logo de todo o ciclo de vida do desenvolvimento;

## Determinar tipos de contagem

*Projeto de Desenvolvimento:* Mede as funcionalidades providos para o usuário na primeira instalação da aplicação;
*Projeto de Manutenção:* Mede as modificações, exclusões e inclusões de funções na aplicação;
*Aplicação:* Mede a aplicação já desenvolvida também conhecido como ponto de função instalado. São revisto sempre que as aplicações sofrem manutenção;

## Escopo e Fonteira

O escopo da contagem define a funcionalidade que será incluída na contagem.
A fronteira da aplicação determina o software sendo dimensionado e o ambiente do usuário ou aplicação externas. É determinado sempre pelo ponto de vista do usuário.
Pode haver mais de uma aplicação incluida no escopo de um único projeto. Se este for o caso várias fronteiras serão identificadas.
**Cuidado**, o posicionamento incorreto da aplicação pode alterar a perspectiva da contagem de uma visão lógica.
Como um mesmo processo elementar pode estar dividido em subprocessamentos distribuídos em mais que uma aplicação podem surgir os seguintes erros de contagem:
* Contagem duplicada da mesma função por várias aplicação;
Dificuldade na determinação do tipo de transação;
* Duplicidade na contagem de arquivos;

## ALI (Arquivo Lógico Interno)

* Grupo de dados ou informação de controle logicamente relacionados;
* Reconhecido pelo usuário;
* Mantido dentro da fronteira da aplicação através do processo elementar;
* Não considerar Code Data

## AIE (Arquivo de Interface Externa)

* Externo e referenciado pela aplicação sendo controlada.

## Classificação das Funções de Dados

**Tipo de Registro**
É um subgrupo dos elementos de dados reconhecido pelo usuário em um ALI ou AIE.

Há 2 tipos de subgrupos:
* Opcional: Usuário tem a opção de utilizar um ou nenhum dos subgrupos durante um processo elementar que adiciona ou cria uma instância do dado.
* Obrigatório: O usuário deve utilizar ao menos um.

Conte um tipo de registro para cada subgrupo opcional ou obrigatório de um ALI ou AIE, se não houver subgrupos conte ALI e AIE como um tipo de registro

**Item de dado:** É um campo único reconhecido pelo usuário e não repedito

**Itens Referenciados / Registros Lógicos**

$ | 1 a 19 | 20 a 50 | 51 ou +
 --- | --- | --- | ---
 1 | Baixa | Baixa | Média
 2 a 5 | Baixa | Média | Alta
 6 ou + | Média | Alta | Alta

**ALI / AIE**

$ | ALI | AIE
 --- | --- | ---
 Baixa | 7 | 5
 Média | 10 | 7
 Alta | 15 | 10
 
## Função de Transição
 
**Processo Elementar**
* Menor atividade que tem significado para o usuário;
* É auto contido, deixando o negócio da aplicação em um estado consistente;

**Entrada Externa**
Processo externo que processa dados ou informações de controle vindo de fora da da fronteira da aplicação.

**Intenção Primária**
* Manter um ou mais ALI's;
* Alterar comportamento do sistema;

**Regras para classificar as EE**
* Arquivos referênciados;
* Contar um ou aquivo para cada ALI mantido;
* Contar um arquivo para cada ALI ou AIE lido;
* ALI lido e mantido contar apenas um arquivo;
* itens de dado referênciados;
* Contar um item para cada campo de entrada ou saída da fronteira da aplicação;
* Contar apenas um item se o mesmo entra e saí da fronteira;
* Contar um item para capacidade de enviar mensagem;
* Contar um item para a capacidade de especificar uma ou mais ações a serem tomadas

**Nível de Complexidade / Arquivos referênciados**

$ | 1 a 4 | 5 a 15 | 16 ou +
 --- | --- | --- | ---
 0 a 1 | Baixa | Baixa | Média
 2 | Baixa | Média | Alta
 3 ou + | Média | Alta | Alta

**Cálculo do PF(Ponto de Função) ajustado**

$ | ALI | AIE | EE
 --- | --- | --- | ---
 Baixa | 7 | 5 | 3
 Média | 10 | 7 | 4
 Alta | 15 | 10 | 6
 
## Saída Externa

Processo elementar cuja inteção primária é enviar dados ou informações de controle para fora da fronteira da aplicação

Regras Adicionais a lógica de processamento (Pelo menos uma)
* Contém ao menos uma fórmula matemática ou cálculo;
* Cria dados derivados;
* Mantém no mínimo um ALI;
* Altera o comportamento do sistema;

**Arquivos Referênciados**

* Contar um arquivo referenciado para cada ALI ou AIE lido;
* Contar um arquivo referenciado para cada ALI ou AIE mantido;
* Contar somente um arquivo referenciado para cada ALI ou AIE;

**Itens de Dados Referenciados**

* Contar um item para cada campo que entra ou sai da fronteira;
* Contar apenas um item se o campo entrar ou sai da fronteira;
* Contar um item para mensagens que entra ou sai da fronteira;
* Contar um item para ação que entra ou sai da fronteira;

**Nível de Complexidade**

$ | 1 a 5 | 6 a 19 | 20 ou +
 --- | --- | --- | ---
 0 a 1 | Baixa | Baixa | Média
 2 a 3 | Baixa | Média | Alta
 4 ou + | Média | Alta | Alta

**Cálculo do PF(Ponto de Função) não ajustado**

$ | ALI | AIE | EE | SE | CE
 --- | --- | --- | --- | --- | ---
 Baixa | 7 | 5 | 3 | 4 | 3
 Média | 10 | 7 | 4 | 5 | 4
 Alta | 15 | 10 | 6 | 7 | 6