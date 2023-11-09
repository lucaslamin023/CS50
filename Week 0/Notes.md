## O que é Ciência da Computação?

A **programação de computadores** é, fundamentalmente, sobre pegar algumas entradas e criar algumas saídas - resolvendo assim um problema. Podemos pensar na resolução de problemas como o processo de pegar algumas informações (detalhes sobre nosso problema) e gerar alguns resultados (a solução para nosso problema). O que acontece entre a entra e a saída, que poderíamos chamar de ***caixa preta***, é a ciência da computação.

![input - output](https://cs50.harvard.edu/x/2023/notes/0/cs50Week0Slide38.png)

  
Para começar a fazer isso, precisaremos de uma maneira de representar entradas (inputs) e saídas (outputs), para que possamos armazenar e trabalhar com informações de ***forma padronizada***.

## Como contamos números?

Podemos contar quantas pessoas compareceram a uma reunião ou quantas frutas estão dentro de uma cesta. Com a nossa mão, usando um sistema  chamado  ***unário***, podemos levantar um dedo de cada vez para representar cada pessoa ou fruta. Porém, não iríamos muito longe assim, então, no dia a dia, utilizamos um sistema mais eficiente para representar números, onde temos dez dígitos, de 0 a 9:

	0, 1, 2, 3 ,4, 5, 6, 7, 8, 9

 - Sistema ***decimal***, onde cada digito pode representar dez valores diferentes

Os computadores utilizam um sistema mais simples, chamado ***binário***,  com apenas dois dígitos possíveis, **0 e 1**, e, é do termo _dígito binário_ que obtemos um termo familiar chamado bit.  Computadores funcionam a base de eletricidade, então podemos dizer que o input físico seria uma corrente elétrica que ativa e desativa pequenos dispositivos eletrônicos, chamados transistores dentro dos processadores. Sendo que, Zeros representam *desligados* e Uns representam _ligados._ Nosso computadores modernos possuem milhões, talvez bilhões, de transistores que são ligados e desligados.

 - Se você, por exemplo, imaginar usar uma lâmpada, uma única lâmpada só pode 
    estar ligada ou desligada, ou seja, contar de **0 a 1**:

		0
		1
  
 - Porém, com três lâmpadas, é possível acendê-las em 8 padrões diferentes,
 possibilitando que contemos de **0 a 7**:

		0 0 0 
		0 0 1
		0 1 0
		0 1 1
		1 0 0
		1 0 1
		1 1 0
		1 1 1

----
 Sabemos, por exemplo, que o número **123** representa cento e vinte e três, por conta que o **3** está 
 na coluna das *unidades*, o **2** está na coluna das *dezenas* e o **1** está na coluna das *centenas*:

		100  10   1
		  1   2   3

 - Portanto,  **123**  é  **100 × 1 + 10 × 2 + 1 × 3 = 100 + 20 + 3 = 123**.


Em binário, com apenas dois dígitos, temos potências de dois para cada valor de casa:

		4 2 1 
		0 0 0 = 0
		0 0 1 = 1
		0 1 0 = 2
		0 1 1 = 3
		1 0 0 = 4
		1 0 1 = 5
		1 1 0 = 6
		1 1 1 = 7

-   Os computadores geralmente usam oito bits, ou um **byte** para representar um número. 
- Se tivéssemos 8 lâmpadas, poderíamos ter um valor binário máximo de 11111111, 
 que teria o valor decimal equivalente a 255:

		128 64 32 16 8 4 2 1  
		  1  1  1  1 1 1 1 1 

- Ou, por exemplo, 50 em binário seria:


		128 64 32 16 8 4 2 1  
		  0  0  1  1 0 0 1 0                                                       
		  

Estamos acostumados com o uso de bytes como uma unidade de medida para dados, como em megabytes, gigabytes e terabytes, para milhões, bilhões e trihões de bytes.


## Texto

  
Assim como os números são padrões binários de uns e zeros, para representarmos as letras, tudo o que 
precisamos fazer é *mapear* letras específicas para números específicos. Por algum motivo, decidiu-se 
que a letra “A” seria o número 65, e “B” o número 66 e assim por diante.

- O mapeamento padrão, [**ASCII**](https://pt.wikipedia.org/wiki/ASCII), também inclui letras minúsculas e pontuação:

![ASCII](https://cs50.harvard.edu/x/2023/notes/0/cs50Week0Slide93.png)

Se recebêssemos uma mensagem de texto com um padrão de bits que tivesse os valores decimais **72 , 73 e 33**, esses bits seriam mapeados para as letras **HI!**. 

	    H         I         !
	   72        73        33
	01001000  01001001  00100001
	

-----


 Com o passar do tempo, há cada vez mais formas de nos comunicarmos por texto e os dígitos binários não chegam perto de conseguir representar todos os caracteres que poderiam ser utilizados pelas diferentes linguagens humanas. Com isso, foi criado o padrão [**Unicode**](https://pt.wikipedia.org/wiki/Unicode), que expandiu o número de bits que podem ser transmitidos e compreendidos pelos computadores.

- Com o Unicode, criaram-se [emojis](https://en.wikipedia.org/wiki/Emoji) que usamos, recebemos ou vemos todos os dias. 

	![emoji](https://cs50.harvard.edu/x/2023/notes/0/cs50Week0Slide103.png)
- Quando recebemos um emoji, nosso computador está apenas recebendo um número binário que mapeia para a imagem do emoji baseado no padrão Unicode. Por exemplo, o emoji “tears of joy" ou 😂 é representado pelos bits: 

		000000011111011000000010

## Cores

Para representarmos cores, novamente basta atribuimos cores aos números. Para existem diversos sistemas, o mais comum deles, é o [**RGB**](https://pt.wikipedia.org/wiki/RGB), onde podemos gerar qualquer cor com uma combinação de quantidades específicas de *vermelho, verde e azul*.

![rgb](https://cs50.harvard.edu/x/2023/notes/0/cs50Week0Slide118.png)

 Pegando os números *72, 73 e 33* usados ​​anteriormente para representar em textos, o *"HI!"*. Em imagens essa mesma sequencia de bits representaria um tom claro de amarelo. Sendo o valor vermelho 72, o valor verde 73 e o valor azul 33.

   ![caixa amarela](https://cs50.harvard.edu/x/2023/notes/0/cs50Week0Slide120.png)

- Cada número é um byte, com 256 valores possíveis. Com três bytes, podemos representar milhões de cores.

----

Os pontos, ou quadrados, em nossas telas são chamados de **pixels**,  usando três bytes para representar a cor de cada pixel, podemos criar **imagens**.  A resolução da imagem é a quantidade de pixels, e as imagens são compostas por muitos milhares ou milhões de pixels. Então, quanto mais pixels mais bytes, por conta disso imagens costumam "pesar" *kilobytes* ou *megabytes*.  

Agora, os **vídeos** são compostos por uma sequencia de muitas imagens, que também podemos chamar de *quadros*, gerando a ideia de movimento, algo semelhante a um [flipbook](https://www.youtube.com/watch?v=p3q9MM__h-M). Vídeos costumam ter desde milhões até trilhões bytes.

- No fim, todo formato de arquivo que existe hoje, como *Word, PDF, Excel, PSD, JPEG ou PNG*, 
são apenas um **sistema padrão** que os humanos criaram para representar informações a partir de bits.


## Algoritmos

A programção de computadores é, essencialmente, a resolulção de problemas por meio de **algoritmos**, que chamamos de *caixa preta* no início do texto. Algoritmos, não passam de uma **sequência de passos** bem definidos, que quando executados, realizam uma tarefa específica. Nós também podemos, mecanicamênte, seguir algoritmos, como seguir a receita para cozinhar um bolo ou utilizar um manual para fazer a instalação de um dispositivo.

![algoritmo](https://files.tecnoblog.net/wp-content/uploads/2019/10/fluxograma-lampada-700x394.jpg)

---
Agora, imaginando um problema antigo como encontrar um nome em uma lista telefônica. Como fazer isso?

- Poderiamos simplesmente ler página por página, procurando o nome, até chegar à última página, algo como:
					
		Pegue a lista telefônica
		Abra na primeira página
		Verifique a página
		Se a pessoa estiver  na página
			Ligar para pessoa
		Se não
			Passe para próxima página
			Volte para linha 3
		Se não
			Abandonar

-   Outra abordagem poderia ser folhear duas páginas por vez, porém mas esse algoritmo estaria incorreto, 
     pois  há uma chance de pularmos a página com o nome que procuramos.  Para resolver isso, podemos voltar 
     uma página se formos longe demais, pois sabemos que a lista telefônica está classificada em ordem alfabética.

		Pegue a lista telefônica
		Abra na primeira página
		Verifique a página
		Se a pessoa estiver  na página
			Ligar para pessoa
		Se não
			Passe duas páginas
			Volte para linha 3
		Se não, caso tenha pulado a letra do nome
			Volte para página anterior
		Se não
			Abandonar
			
 - Porém, sabendo que lista está classificada em ordem alfabética, podemos usar uma abordagem final e mais eficiente, que seria abrir a lista no meio e verificar se nosso nome estará na metade esquerda ou na metade direita do livro, e repetimos isso até encontrarmos o nome em questão, cortando o problema pela metade a cada operação:

		Pegue a lista telefônica  
		Abra no meio da lista telefônica  
		Olhe para a página  
		Se a pessoa estiver na página  
			Ligar para pessoa  
		Se não, caso a pessoa estiver mais para o início do livro  
			Abrir no meio da metade esquerda do livro  
			Volte para a linha 3  
		Se não, caso a pessoa estiver mais para o final do livro  
			Abrir no meio da metade direita do livro  
			Volte para a linha 3  
		Caso contrário  
			Abandonar
			
- Cada uma dessas abordagens poderia ser chamada de algoritmos. A velocidade de cada um desses algoritmos pode ser representada da seguinte forma: 

![grafico de algortmos](https://cs50.harvard.edu/x/2023/notes/0/cs50Week0Slide141.png)

Nossa primeira solução, pesquisar uma página por vez, pode ser representada pela linha vermelha: nosso tempo para resolver aumenta linearmente à medida que o tamanho do problema aumenta.  _n_  é um número que representa o tamanho do problema, portanto, com n páginas em nossas listas telefônicas, temos que realizar até n etapas para encontrar um nome.

A segunda solução, pesquisar duas páginas por vez, pode ser representada pela linha amarela: nossa inclinação é menos acentuada, mas ainda linear. Agora, precisamos apenas de (aproximadamente)  _n / 2_  etapas, já que viramos duas páginas de cada vez.

Nossa solução final, dividindo a lista telefônica ao meio a cada vez, pode ser representada pela linha verde, com uma relação fundamentalmente diferente entre o tamanho do problema e o tempo de resolvê-lo:  [logarítmica](https://ead.napratica.org.br/enrollments/9122808/courses/84414/course_contents/%E2%80%9Dhttps://pt.wikipedia.org/wiki/Logaritmo%E2%80%9D)  , já que nosso tempo de resolução aumenta cada vez mais lentamente conforme o tamanho do problema aumenta.


- Em uma lista com 1024 páginas, precisaríamos de apenas 10 etapas de divisão ao meio até termos uma página restante para verificar, podemos visualizar em uma [animação de dividir uma lista telefônica ao meio](https://www.youtube.com/watch?v=F5LZhsekEBc). Em comparação com a [animação de pesquisar uma página por vez](https://www.youtube.com/watch?v=-yTRajiUi5s), onde seria necessário 1023 operações até chegarmos na última página.
---

## Scratch

O Scratch é uma linguagem gráfica de programação baseada em blocos que funciona como um quebra-cabeça, nele você tem a sua disposição coisas como:


- Funções
- Condições
- Expressões booleanas
- LoopingS
- Váriáveis
- Eventos

Além disso, podemos adicionar sons, gerar movimento e criar nossos próprios blocos. Com tudo isso é possível criar animações, jogos e histórias interativas em uma interface de códigos bem amigável:


![scratch](https://edools-3-production.s3.amazonaws.com/org-6988%2Fschool-7227%2F3d4d6b018f0dca2a36420b19df5a667a%2Fscratch.png)

O primeiro conjunto de problemas propôs a criação de um projeto de escolha própria, seguindo os requisitos:


- Seu projeto deve usar pelo menos dois sprites, dos quais pelo menos um não deve ser um gato.
- Seu projeto deve ter pelo menos três scripts no total (ou seja, não necessariamente três por sprite).
- Seu projeto deve usar pelo menos uma condicional, pelo menos um loop e pelo menos uma variável.
- Seu projeto deve usar pelo menos um bloco personalizado que você mesmo criou (via Make a Block ), que deve receber pelo menos uma entrada.
- Seu projeto deve ser mais complexo do que a maioria daqueles demonstrados em palestras (muitos dos quais, embora instrutivos, foram bastante curtos), mas pode ser menos complexo do que [Oscartime](https://scratch.mit.edu/projects/16733/) e [Ivy's Hardest Game](https://scratch.mit.edu/projects/26329347/).

--- 
- [Meu Projeto Scratch](https://scratch.mit.edu/projects/920834556)