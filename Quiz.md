# Compilers Quiz
## CEFSA - FTT - EC

- Use notação **markdown** para responder
- Faça um **fork** e depois **pull request**

1) Qual a diferença entre uma linguagem compilada e uma linguagem interpretada? Cite exemplos de linguagens.


__R: Primeiramente, é importante lembrar que todo código de alto nível passa por algum tipo de compilação, senão ele não poderá ser executado. A diferença principal entre um e outro está em COMO e QUANDO essa compilação é feita.__

__Uma linguagem compilada é, como o próprio nome diz, compilada e transformada código de máquina, gerando um arquivo de saída pronto para execução. Então, pode ser executado diretamente pelo sistema operacional/processador, não precisando mais do código-fonte.__

_(Tenha como exemplo os trabalhos feitos no semestre anterior com Arduino: era escrito um código no computador desktop. Então, mandava-se compilar e, depois, o arquivo compilado era armazenado dentro do processador do Arduino. Assim, era possível executar o programa até mesmo sem estar conectado ao PC)_

__Linguagens interpretadas são dinâmicas, ou seja, a compilação e a leitura dão-se em tempo de execução e linha a linha. Ao ser lida, gera um arquivo específico que depende de um intermediário (virtual machine da própria linguagem) para interpretar. Então, essa saída é compilada, transformada em código de máquina e executada em tempo real pelo processador.
Por isso, um programa escrito em linguagem interpretada não pode ser separado de seu código-fonte__

__Exemplos:__

_Linguagens interpretadas: Javascript, Lua, Python_

_Linguagens compiladas: Cobol, Fortran, C e Pascal._

_C# e Java podem ser compiladas e interpretadas._

__(REVISÃO: Amanda, Victor)__


__________________________________________________________________________________________________________________________________


2) Quais são os prós e contras entre linguagens compiladas e interpretadas?


__R: Linguagens compiladas previnem que os erros (sintáticos, semânticos, léxicos etc.) cheguem ao código de máquina (erros de runtime não podem ser prevenidos dessa maneira). Além disso, há maior segurança num programa compilado, pois o código-fonte não precisa estar junto para que o programa seja executado.
Elas também oferecem a vantagem de serem otimizadas como um todo, eliminando do arquivo de saída trechos de código que não serão utilizados. Isso porque a análise é feita em blocos e o programa é visto como um todo.
Todavia, o arquivo de saída não oferece flexibidade, ou seja, somente será executado na plataforma/sistema operacional para o qual foi compilado.__

__Linguagens interpretadas não oferecem tanta segurança, pois é possível acessar o código-fonte que, obrigatoriamente, deve estar presente na execução. Elas também podem apresentar diversos erros durante a execução do programa, já que a leitura, interpretação e execução são todas feitas linha a linha. Porém, há maior flexibilidade de execução, podendo ser executado em várias plataformas diferentes e tendo uso muito comum para desenvolvimento web.
Além disso, o código interpretado é otimizado conforme seu uso, ou seja, a cada vez que ele é lido, sua execução é otimizada.__

__(RESPOSTA: Amanda, Victor)__


__________________________________________________________________________________________________________________________________


3) Qual a diferença entre assembler e assembly?


__R: Assembly é uma linguagem de programção de baixo nível mas ainda inteligível pelos programadores, assembler é o programa montador
que transforma as instruções escritas na linguagem assembly para códigos binários e endereços de memória, instruções de baixo nível (instruções de máquina) que serão utilizadas diretamente pelo processador.__

__Cada computador tem seu assembler específico, que é utilizado com um tradutor ("assemblador" -> compilador). Ele é quem gera os código binários e define os endereços de memória.__

__(REVISÃO: Amanda, Victor)__

__________________________________________________________________________________________________________________________________


4) O que é lexema?


__R: O analisador léxico lê um fluxo de caracteres que compõem o programa fonte e os agrupa em seqüências significativas, chamadas lexemas.  Observe que, sendo sequências significativas, um lexema constitui a menor unidade significativa da análise léxica. Isso não significa que ele é um caracter (nessa comparação, está muito mais próximo de cada palavra lida).__

__ATENÇÃO: "lexema" e "token" não são a mesma coisa! [Melhores explicações sobre Patterns nos exemplos da resposta 26]__

_Para cada lexema, o analisador léxico produz como saída um token no formato. O token é uma unidade léxica reconhecida por uma regra (conhecida como "Padrão"). De modo grosseiro, o token é algo como a classificação do lexema._

_É composto pelo seguinte formato: <nome [, valor]> ( entre colchetes é opcional, vai depender se o token tem argumento ou não). O __nome__ é, basicamente, o "tipo" do lexema a ser classificado (não se esqueça que estamos "classificando" um lexema). Ele pode ser escrito por extenso ou identificado com um número. O __valor__ é o valor do próprio lexema, ou seja, sua palavra, ou o endereço onde ela está referenciada na tabela de lexemas._

_Exemplo:_

_Pense na seguinte sentença:          "string exemplo = "Olá Mundo"_

_Temos os seguintes lexemas:_

| Posição | Lexema |
| ---|---| 
| 1 | string |
| 2 | exemplo |
| 3 | = |
| 4 | Olá Mundo |

_Vamos pensar primeiramente no lexema 4 - Olá Mundo : mesmo sendo duas palavras, formam apenas um lexema, pois as duas palavras são atribuídas para a mesma variável ("exemplo"). Assim, o token desse lexema seria algo como <literal, Olá Mundo>
(observe que estamos falando de um analisador sintático, portanto, ainda é muito cedo para classificar o tipo como string, char etc., trata-se apenas de um literal. Se tratando de números, a regra permanece: não há decimal, integer, double etc., são todos classificados apenas como "número". Nomes de variáveis, funções, parâmetros de funções são chamados de "identificadores")._

_Agora, se analisarmos o lexema 3- =, teremos o seguinte token <=,>. O "=" já tem um significado próprio, é um token de relação. Portanto o compilador saberá que, ao se deparar com um símbolo de igual ele fará alguma atribuição a uma variável. Portanto, esse token não tem valor/argumento._


__(RESPOSTA: Raquel Sales / REVISÃO: Amanda, Victor)__


__________________________________________________________________________________________________________________________________


5) Qual é o autômato finito que representa a expressão regular: [a-zA-Z_0-9] e o que ela está reconhecendo?

__________________________________________________________________________________________________________________________________

6) Porque é interessante desenvolver programas em linguagem de alto nível ao invés de utilizar direto código de máquina? 

__R: Porque a linguagem de alto nível é mais intuitiva ao usuário, sendo assim mais produtiva e inteligível. Ao invés de digitar inúmeras linhas na linguagem de baixo nível, o usuário pode apenas chamar funções prontas - que ele consiga entender o intuito - na linguagem de alto nível.__

__________________________________________________________________________________________________________________________________

7) Estabeleça uma regra para criar nomes de variáveis em uma linguagem de programação, e defina sua expressão regular e autômato finito.

__________________________________________________________________________________________________________________________________

8) Qual a diferença entre analisador sintático e semântico?
__R: O analisador sintático prepara a árvore sintática e a encaminha ao analisador semântico que analisa os lexemas separados, verificando a semântica gerada anteriormente. Enquanto o analisador sintático verifica se os tokens pertencem à linguagem livre de contexto, a semântica verifica se os valores e as declarações correspondem ao padrão solicitado.__

__________________________________________________________________________________________________________________________________

9) Explique o analisador semântico.
__R: Verifica os erros semânticos referentes ao escopo em que uma variável foi declarada, fazendo a ligação entre seu tipo, nome e valor, além de  validação de tipo. Ex: Correspondência entre declarações de variáveis.__

__________________________________________________________________________________________________________________________________

10) Quais as fases de compilação?

__R: Análise e Síntese. (Sub-fases descritas na questão 16) ~Raquel Sales__

__________________________________________________________________________________________________________________________________

11) Onde as linguagens de programação, regexp e os idiomas (inglês, português e francês) se encaixam na hierarquia de Chomsky?
__R: Os idiomas estão contidos na categoria 0, recursivamente enumeraveis e identificados apenas pelo maquina de Turing. As linguagens de programação se encontram na categoria 2, reconhecidas por automatos finitos com pilha e o regexp se encontra na categoria 3 reconhecida por autômato finito, pois são as linguagens regulares.__

__________________________________________________________________________________________________________________________________

12) Como se chama um programa que converte uma linguagem de programação de alto nível em outra, e porque isso é interessante?

__R: É chamado de transpilador (ou Source-to-source compiler), ele é interessante pois podemos escrever código em versões
melhoradas de linguagens que não são suportadas nativamente pelo sistema e então transpilar esses códigos para algo que
o sistema suporte.
Exemplos: Sass e Less para Css, Jade para HTML, TypeScript para JavaScript, EcmaScript 8 para versões anteriores, etc. ~Laion__

__________________________________________________________________________________________________________________________________

13) O que são OPCODEs e mnemônicos? 

__R: OPCODEs são codigos de operação que identificam uma instrução que será realizada pelo processador. Assim, é possível enviar comando diretamente para o processador.
Mnemônicos são sequencias de caracteres que lembram uma palavra e podem executar um OPCODE. A ideia, como o próprio nome sugere (a palavra "mnemônico" significa "relativo à memória"), serve para trazer a memória, lembrar facilmente o comando o processador executará em vez de ter que memorizar um código numérico e sua respectiva ação__

__(REVISÃO: Amanda, Victor)__

__________________________________________________________________________________________________________________________________

14) O que pode ser programado em assembly que não pode ser feito em linguagens de alto nível?

__R: Nada. ~Raquel Sales__
__R: Qualquer programação em assembly pode ser feita com linguagem de alto nível, pois as instruções contidas nestas linguagens representam uma série de instruções em assembly de modo que otimize o tempo de programação e facilite a manutenção e interpretação do código. Além disso, de acordo com a Lei de Moore, qualquer linguagem de programação com instruções sequenciais, loops e condições (como assembly e nas linguagens de alto nível), permite a criação de qualquer programa. ~Bruno Chaves__

__________________________________________________________________________________________________________________________________

15) Porque há engenheiros que programam em assembly atualmente?

__R: Existem engenheiros que programam em assembly atualmente pois em alguns momentos do desenvolvimento de código C, os profissionais acabam percebendo que certos pedaços do código estão com uma performance menor do que a esperada, logo este trecho do código é convertido para linguagem assembly, melhorando assim sua performance.
Além disso também existem alguns microcontroladores que só podem ser programados em linguagem assembly.__

__________________________________________________________________________________________________________________________________

16) Explique cada uma das fases de compilação.

__R: Análise Sintática:__
 - Verifica a estrutura gramatical da tabela gerada pela analise lexica;
 - Verifica se a sentença pertence a linguagem;
 - Recebe os tokens e gera árvore de derivação (Observação: os tokens são os símbolos terminais da GLC).__

__Análise semântica:__
 - A informação é adiciada a árvore;
 - Verificação de tipos e erros;
 - Verifica inicialização de variáveis;
 - Verifica tipos de objetos;
 - Prepara a geração de códigos. ~Raquel Sales__
 
__R: Análise Lexica:__
 - lê o arquivo de código fonte
 - ela faz o papel do Scanner que por sua vez, analisa caracter por caracter até achar um caracter de parada, geralmente um espaço ou um; conforme a sintaxe da linguagem.
 - Assim reconhece como um lexima e o coloca em uma tabela de leximas(tokens)
 - Ela pode reconhecer por exemplo, se um nome de uma variavel está iniciando com um número por meio de uma regexp e emitir 
 um erro. ~Bruno N.__

__________________________________________________________________________________________________________________________________

17) Explique processador RISC e CISC.
__R: Processador Cisc (Complex Instruction Set Computer) é capaz de executar centenas de instruções complexas e mais rapidamente, enquanto que o Risc (Reduced Instruction Set Computer) consegue executar poucas instruções simples por vez, ~~por essa razão ele se torna
mais barato~~. ~Michele.__

__R: Without commercial interest, processor developers were unable to manufacture RISC chips in large enough volumes to make their price competitive. [RISC vs. CISC](https://cs.stanford.edu/people/eroberts/courses/soco/projects/risc/risccisc/)__

__________________________________________________________________________________________________________________________________

18) Qual a diferença entre linguagens estáticas e dinâmicas, cite linguagens destes dois tipos.

__R: A diferença está relacionada a uma "exigência" da linguagem na declaração de suas variáveis. Nas linguagens estáticas, ao se declarar uma variável, o tipo deve ser obrigatoriamente informado. Quando houver uma atribuição de valor, o compilador se encarrega de verificar se o dado informado corresponde ao tipo declarado. Nas linguagens dinâmicas não é necessário declarar o tipo da variável. Nesse caso, a correspondência entre o valor atribuído à uma variável e seu tipo é feita em tempo de execução,  não durante a compilação. Java e C# são linguagens estáticas, enquanto JavaScript, Python, Ruby e PHP são linguagens dinâmicas. ~Armando Dias.__

__________________________________________________________________________________________________________________________________

19) Os seguintes termos se aplicam a quais linguagens de programação?

| ID | Tipo |
| ---|---| 
| A | Imperativo |
| B | Declarativo |
| C | Dinâmica |
| D | OO |
| E | Funcional |
| F | 3G |
| G | 4G |
 
 | ID | Linguagem |
 | --- | --- |
 | 1 | C |
 | 2 | C++ |
 | 3 | COBOL |
 | 4 | Fortran |
 | 5 | Java |
 | 6 | Lisp |
 | 7 | SQL |
 | 8 | Perl |
 | 9 | Python |
 |10 | VB |

__________________________________________________________________________________________________________________________________

20) O que é e dê exemplos de linguagens dinamicamente tipadas.

__R: são linguagens que o tipo da variavel não é determinada quando declarada, ela assume o tipo de acordo com o codigo.
Exemplo: Javascript.__

__________________________________________________________________________________________________________________________________

21) O que são linguagens fortemente tipadas e fracamente tipadas? Cite exemplos.
__R:Linguagens fortemente tipadas são linguagens que exigem que na declaração da variável o seu tipo seja obrigatoriamente explicitado. Como por exemplo, na linguagem Java devemos escrever as variáveis da seguinte maneira:
	int numero = 0;
		String texto = “olá mundo”;
	Boolean flag = true;
São exemplos de linguagens fortemente tipadas: Java, C#, C++, C, COBOL, Fortran.
Já nas linguagens fracamente tipadas o programador não deve explicitar o tipo da variável pois a linguagem é capaz de identificar o tipo da variável de acordo com o valor que a variável assume em tempo de execução do programa. Nas linguagens com essa tipagem, uma variável pode alterar seu tipo quantas vezes forem necessárias, sempre de acordo com o valor que recebe. Abaixo um exemplo de como são declaradas as variáveis em Javascript, que é uma linguagem fracamente tipada.

__R:|	x = 5
	ou 
	var x = 5|
Neste caso, o programa assume que a variável x é do tipo int.
	__R:|y = ”ola mundo”
	ou
	var y = “ola mundo”|
	Neste caso o programa assume que a variável y é do tipo string.
São exemplos de linguagens fracamente tipadas: PHP, Javascript, Ruby, Python.

__________________________________________________________________________________________________________________________________

22) O que é um bloco de código?
__R: Blocos de código são um conceito existente há muito tempo em linguagens xBase. Não como algo que apareceu da noite para o dia, e sim uma evolução progressiva utilizando a combinação de muitos conceitos da linguagem para a sua implementação.

__R: Conjunto de ações (linhas de código) a serem executadas, delimitadas por um símbolo (geralmente colchete - {...código...}).__
__É comum haver blocos dentro de blocos, como no caso dos laços de repetição encadeados__

__(RESPOSTA: Amanda, Victor)__

__________________________________________________________________________________________________________________________________

23) Porque variáveis devem ser inicializadas antes do uso?

__R: As variáveis são apontadores para endereços de memória. Devem ser inicializadas antes de ser atribuídas pois precisam realizar um alocamento de memória compatível com o dado que será guardado. Não há como armazenar um objeto criado a partir de uma classe em uma variável que alocou memória suficiente para um tipo Inteiro. ~Jorge Henrique__

__________________________________________________________________________________________________________________________________

24) SQL é uma linguagem declarativa ou imperativa? Porque?

__R: SQL é uma linguagem declarativa. Por que você especifica como quer o resultado, mas exatamente como o banco de dados irá achar o resultado desejado é problema dele. SQL padrão não é uma linguagem de programação. Com algumas extensões pode ser. Uma linguagem imperativa é aquele que o programador define como o algoritmo deve funcionar. Felipe__

__________________________________________________________________________________________________________________________________

25) Quais as duas partes/fases principais de um compilador?

__________________________________________________________________________________________________________________________________

26) Qual a diferença entre tokens, patterns e  lexema.
__R;Tokens, patterns e lexemas são termos relacionados a implementação de um analisador léxico.
Token – É um par composto pelo nome do token e um valor de atributo (opcional).  O nome do token é sempre um símbolo abstrato que representa a unidade léxica, por exemplo: Palavras reservadas, números, identificadores e etc.
Padrão – É a forma que os lexemas de uma cadeia de caracteres podem assumir, por exemplo: o padrão de uma palavra reservada é a sequência de caracteres que fazem parte da formação da palavra; O padrão de um identificador é a sequência de caracteres que fazem parte da formação dos nomes de variáveis e funções.
Lexema – É uma sequência de caracteres reconhecidos por um padrão.

__Para cada lexema, o analisador léxico produz como saída um token no formato. O token é uma unidade léxica reconhecida por uma regra (conhecida como "Padrão"/"Pattern"). De modo grosseiro, o token é algo como a classificação do lexema._

__É composto pelo seguinte formato: <nome [, valor]> ( entre colchetes é opcional, vai depender se o token tem argumento ou não). O__ _nome_ __é, basicamente, o "tipo" do lexema a ser classificado (não se esqueça que estamos "classificando" um lexema). Ele pode ser escrito por extenso ou identificado com um número. O__ _valor_ __é o valor do próprio lexema, ou seja, sua palavra, ou o endereço onde ela está referenciada na tabela de lexemas.__

_Exemplo:_

_Pense na seguinte sentença:          "string exemplo = "Olá Mundo"_

_Temos os seguintes lexemas:_

| Posição | Lexema |
| ---|---| 
| 1 | string |
| 2 | exemplo |
| 3 | = |
| 4 | Olá Mundo |

__Vamos pensar primeiramente no lexema 4 - Olá Mundo : mesmo sendo duas palavras, formam apenas um lexema, pois as duas palavras são atribuídas para a mesma variável ("exemplo"). Assim, o token desse lexema seria algo como <literal, Olá Mundo>
(observe que estamos falando de um analisador sintático, portanto, ainda é muito cedo para classificar o tipo como string, char etc., trata-se apenas de um literal. Se tratando de números, a regra/Padrão determina o reconhecimento apenas pela sequência de carcateres numériccos, com pontos ou vírgula. Nomes de variáveis, funções, parâmetros de funções são classificados pela sequência seguida de caracteres e são chamados de "identificadores").__

__Agora, se analisarmos o lexema 3- =, teremos o seguinte token <=,>. O "=" já tem um significado próprio, é um token de relação. Portanto o compilador saberá que, ao se deparar com um símbolo de igual ele fará alguma atribuição a uma variável. Portanto, esse token não tem valor/argumento.__


__(RESPOSTA: Amanda, Victor)__

__________________________________________________________________________________________________________________________________

27) Explique a fase de análise léxica.

__________________________________________________________________________________________________________________________________

28) Escreva uma expressão reguar que reconheça números ponto flutuantes: 1.2, 3, 4.50, .03, 0.000032, -0.2, +3.0014

__________________________________________________________________________________________________________________________________

29) Porque estudamos compiladores?

__________________________________________________________________________________________________________________________________

30) Qual a diferença do Scanner e Parser?
__R: O Scanner realiza a análise dos símbolos inseridos no código e é ligado ao processo de análise léxica. Já o Parser tem a função de verificar o conjunto de símbolos e está ligado ao processo semântico de compilação.

__________________________________________________________________________________________________________________________________

31) Que tipo de linguagem pode ser reconhecida pela máquina de Turin?

__R: A ideia é que qualquer linguagem regular possa ser reconhecida pela máquina de Turin__

__(RESPOSTA: Amanda, Victor)__

__________________________________________________________________________________________________________________________________

32) Com base na figura abaixo, explique o processo de compilação:







33) Qual a diferença entre erro de sintaxe e erro semântico?
__R: A diferença entre um erro de sintaxe e um erro semântico é que no erro sintático ele apresenta um erro quando não consegue entender aquela instrução escrita, como por exemplo estar escrito “FORM” ao invés do “FROM” em uma consulta do SQL. Já no erro semântico, se trada de quando compilador não entende o significado daquilo escrito no código.

__________________________________________________________________________________________________________________________________

34) Write a regexp that accepts all strings of a's and b's that do not contain the subsequence “abb”.
__R:^(a(?!(b{2}))|b)+$

__________________________________________________________________________________________________________________________________

35) Escreva uma expressão regular que reconheça vogais em letras maiúsculas e consoantes em legras minúsculas

__________________________________________________________________________________________________________________________________

36) Exercise 3.3.4 : Most languages are case sensitive, so keywords can be written only one way, and the regular expressions describing their lexemes are very simple. However, some languages, like SQL, are case insensitive, so a keyword can be written either in lowercase or in uppercase, or in any mixture of cases. Thus, the SQL keyword SELECT can also be written select, Select, or sElEcT, for instance. Show how to write a regular expression for a keyword in a case-insensitive language. Illustrate the idea by writing the expression for select in SQL.

__________________________________________________________________________________________________________________________________
 
37) Qual a diferença entre erro de sintaxe e erro semântico?

__________________________________________________________________________________________________________________________________

38) Write a regexp that accepts all strings of digits with no repeated digits. Hint: Try this problem with a few digits, such as {0; 1; 2}.

__________________________________________________________________________________________________________________________________

39) Que tipo de linguagem o NFA e DFA podem reconhecer?

__________________________________________________________________________________________________________________________________

40) Qual é a expressão regular para o autômato:



__________________________________________________________________________________________________________________________________

41) Escreva um autômato que reconheça: A|E JK U|O

__________________________________________________________________________________________________________________________________

42) Escreva um autômato que reconheça: 
```html
<H1>
```
e
```html
</H1>
```
*Respostas na bibliografia, "Livro do Dragão" na biblioteca virtual* e físico na biblioteca "Compiladores - Princípios, Técnicas e Ferramentas, Sethi,Ravi, Aho,Alfred V."

