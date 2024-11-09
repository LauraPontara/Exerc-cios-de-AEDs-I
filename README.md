# Listas de exercícios da disciplina de Algoritmos e Estrutura de Dados I
### Lista 6 - Recursividade

1. Escreva um programa com uma função recursiva que calcule o valor da série:
  (1/2) + (3/4) + (5/6) + ... + (n-1)/n.
   O número \( n \), a ser lido, deve ser sempre par.

2. Faça uma função recursiva para calcular a potência entre dois números inteiros \( x \) e \( y \) (pot = x^y).
   Não use a função `pow()` pronta do C.

3. Escreva uma função recursiva que calcule a soma dos dígitos de um inteiro estritamente positivo \( n \). 
   A soma dos dígitos de 132, por exemplo, é 6. Não use vetor!

4. Faça uma função recursiva, em linguagem C, que calcule o valor da série \( S \) descrita a seguir para um valor \( n > 0 \) a ser fornecido como parâmetro para a mesma.
   
   ![image](https://github.com/user-attachments/assets/6e27f5ce-9301-467d-ae05-a78ee728f1c6)
   
6. Faça uma função recursiva que receba um número inteiro positivo par \( N \) e imprima todos os números pares de 0 até \( N \) em ordem decrescente.

7. Uma das maneiras de se conseguir a raiz quadrada de um número é subtrair do número os ímpares consecutivos a partir de 1, até que o resultado da subtração seja menor ou igual a 0 (zero).
   O número de vezes que se consegue fazer a subtração é a raiz quadrada exata (resultado = 0) ou aproximada do número (resultado negativo).
   Exemplo: raiz quadrada de 16 = 4
  (16 -1 = 15 – 3 = 12 – 5 = 7 – 7 = 0)

   4 subtrações.
   Implemente um programa que calcule e imprima a raiz quadrada de um número fornecido via teclado. Use recursividade para resolver este exercício.

9. Um problema típico em ciência da computação consiste em converter um número da sua forma decimal (base 10) para a forma binária. Por exemplo, o número 12 tem a sua representação binária igual a 1100. A forma mais simples de fazer isso é dividir o número sucessivamente por 2, onde o resto da i-ésima divisão vai ser o dígito \( i \) do número binário (da direita para a esquerda).
   Exemplo:
  12 / 2 = 6  resto 0 (1º dígito da direita para esquerda)
  6 / 2 = 3, resto 0 (2o dígito da
direita para esquerda),
  3 / 2 = 1 resto 1 (3o dígito da direita para esquerda), 1 / 2 = 0 resto 1 (4o
dígito da direita para esquerda). Resultado: 12 = 1100

    Escreva um método recursivo `Dec2Bin(int decimal)` que dado um número decimal imprima a sua representação binária corretamente.
#
### Lista 7 - Arrays

Dicas
* Exemplo de uso da Função rand para geração de número aleatórios entre 0 e 99.
   ![image](https://github.com/user-attachments/assets/5e38c2d6-12b6-42d8-82e4-230cbcda4959)

1. Escreva um programa para preencher um vetor com 20 vinte valores inteiros (os valores podem
ser lidos do teclado ou gerados automaticamente). Em seguida, o sistema deve solicitar ao
usuário um valor, que deve ser pesquisado no vetor. Imprima as posições do vetor que armazena
o valor informado.

2. Escreva um programa que preencha um vetor de tamanho 100 com os 100 primeiros números
naturais que não são múltiplos de 6 e que não terminam com 6.
Atenção: todas as 100 posições do vetor devem ser preenchidas.

3. Escreva um algoritmo que:
(a) Crie um arranjo de 5 elementos inteiros e o preencha de números
(b) Procure a posição do menor elemento deste arranjo
(c) Troque o menor elemento com elemento da primeira posição
(d) Imprima os elementos do arranjo
Cada um dos itens acima devem ser implementados em funções ou procedimentos separados que
recebem o vetor por parâmetro

4. Escreva um programa que receba do usuário dois vetores, A e B, com 10 números inteiros cada.
Crie um novo vetor, C, calculando C = A - B. Mostre na tela os dados do vetor C.

5. Implemente um procedimento preencheValores que preencha um vetor X de 10 elementos. Na
sequência, faça um procedimento copiaNegativos que receba um vetor preenchido, teste e copie
todos os valores negativos deste vetor para um novo vetor, sem deixar elementos vazios entre os
valores copiados. O vetor contendo números negativos deve conter até 10 elementos - após o
último número negativo (caso não existam 10 número negativos) o vetor deve conter o número
0. Faça um programa (main) que acione os procedimentos e imprima o vetor de números
negativos, sem imprimir o valor zero.

```c
void preencheValores(int vetor[], int length);
void copiaNegativos(int vetor[], int length, int vetorNeg[]);
```
6. Escreva um programa que preencha e imprima na tela um vetor de tamanho 50, cujos valores
são dados pela seguinte fórmula:
𝑝𝑜𝑠 = (𝑖 + (3 × 𝑖) )% (𝑖 + 1)
onde i corresponde à posição do elemento no vetor.

7. Escreva um programa que leia da entrada padrão 5 números reais, que devem ser armazenados
em um arranjo. Em seguida, gere outro arranjo, cujos valores correspondem ao dobro dos
respectivos elementos do primeiro arranjo.

8. Escreva um vetor de inteiros A com 10 elementos. Em seguida, leia um vetor de inteiros B,
também com 10 elementos. Durante a leitura do vetor B, se o elemento na posição i for igual ao
elemento na mesma posição do vetor A, rejeitar o valor e solicitar a entrada de um novo valor. A
rejeição deve ocorrer até que o valor seja digitado um valor válido. Após a leitura dos vetores A e
B, criar um algoritmo que calcule e imprima a diferença entre cada um dos elementos.

9. Escreva um programa que armazene as idades dos alunos que estão presentes em uma aula da
disciplina de Algoritmos e Estrutura de Dados I. Considere que o vetor possa conter até 60 registros. Sabe-se que, em uma dada aula, alguns alunos podem ter faltado. Com isso, leia
elementos até que seja digitado um valor 0 ou enquanto a quantidade de alunos for inferior à
capacidade do vetor. Imprima:
* Idade de todos os alunos presentes na aula (não imprimir idades não cadastradas).
* Idade de todos os alunos com idade superior à média.
#

### Lista 8 - String, Matriz e Ponteiro

1. Escreva um programa que leia do teclado uma string S. Gere uma string I, com os caracteres
em ordem contrária.
Ex.: S = “Abacate”, I = “etacabA”

2. Desenvolva um programa para criptografar uma string. Para isso, solicite ao usuário uma
chave k, correspondente a um número inteiro. Para criptografia, obtenha o número ASCII de
cada uma das letras e some a cada uma delas o valor à chave k. Converta a letra obtida
novamente para string, para gerar a letra criptografada.
Dica: Para evitar que a soma seja superior a 255, fora do intervalo da tabela ASCII, divida o
valor da soma por 255.
Ex.: Lcripto = (L + k) % 255, onde L = ASCII da letra

3. Desenvolva um programa para decriptografar a string gerada no exercício 2

4. Leia uma cadeia de caracteres e converta todos os caracteres para maiúscula. Dica: subtraia
32 dos caracteres cujo código ASCII está entre 65 e 90.
   
5. Escreva um programa que, a partir de um nome informado pelo usuário, exiba suas iniciais.
As iniciais são formadas pela primeira letra de cada nome, sendo que todas deverão aparecer
em maiúsculas na saída do programa. Note que os conectores e, do, da, dos, das, de, di, du
não são considerados nomes e, portanto, não devem ser considerados para a obtenção das
iniciais. As iniciais devem ser impressas em maiúsculas, ainda que o nome seja entrado todo
em minúsculas. Exemplos:
José Carlos Souza => JCS
Nome do Fulano => NF
Heloísa Martins Vieira => HMV

6. Palíndromo. Um palíndromo é uma sequência de caracteres cuja leitura é idêntica se feita da
direita para esquerda ou vice−versa. Por exemplo: OSSO e OVO são palíndromos. Em textos
mais complexos os espaços e pontuação são ignorados. A frase SUBI NO ONIBUS é o
exemplo de uma frase palíndroma onde os espaços foram ignorados. Faça um programa que
leia uma sequência de caracteres, mostre−a e diga se é um palíndromo ou não.

7. Desenvolva um programa em C que leia uma matriz de 5x4 contendo as seguintes
informações sobre 5 alunos de uma disciplina:
• Primeira coluna: números de matrícula;
• Segunda coluna: média das provas;
• Terceira coluna: média dos trabalhos;
A quarta coluna é composta pela nota final de cada aluno e deve ser calculada através da
soma da média das provas com a média dos trabalhos. Por fim, imprima a matrícula do
aluno com a maior nota final e a média aritmética das notas do 5 alunos.

8. Escreva um programa em C que declare variáveis para armazenar um valor inteiro, um valor
real e um caracter. Deve existir no programa ponteiros associados a cada um deles. O
programa deve solicitar novos dados para as variáveis e elas devem ser modificadas usando
os respectivos ponteiros. Exiba os endereços e os conteúdos de todas as variáveis e ponteiros
antes e após a alteração.

9. Implemente um procedimento que calcule o comprimento e a área de uma circunferência de
raio R. Esse procedimento deve obedecer ao cabeçalho a seguir:
void calcCircunferencia (float R, float *compr, float *area)
A área da superfície e o volume são calculados pelas equações:
C=2*PI*R e A =PI*R^2

No programa principal faça a leitura do raio, acione o procedimento e exiba os resultados do
comprimento e área calculados por ele.

10. Mostre na tabela a seguir todas as alterações dos conteúdos das variáveis (teste de mesa) e
identifique qual será a saída do programa em C para os valores lidos (x = 5 e y = 6).
```c
void func(int *px, int *py)
{
px = py;
*py = (*py) * (*px);
*px = *px + 2;                                                 
}
int main ()
{
int x, y;
scanf(“%d”,&x);
scanf(“%d”,&y);
func(&x,&y);
printf(“x = %d, y = %d”, x, y);
return 0;
}
```
 ![image](https://github.com/user-attachments/assets/0b763c5c-204a-4970-99d3-59b2b01f08fd)

11. Desenvolva um programa que instancie um vetor de inteiros A utilizando malloc. O programa
deve ler um valor k, onde k é positivo e menor que o tamanho do vetor (rejeite entradas
inválidas). Implemente um procedimento que receba como parâmetros o vetor A, o tamanho
do vetor |A| e o valor k. Retorne o k-ésimo menor elemento do vetor.

Ex.: A = {3, 5, 7, 8 ,12, 14, 15, 16}, k = 3, retorno = 7.

12. Escreva um programa que leia do teclado um valor n. Instancie, usando o comando malloc,
uma matriz de números em ponto flutuante Mn×n. Preencha a matriz com valores aleatórios e
imprima seus elementos.

13. Escreva um programa para preencher uma matriz M4×4. Em seguida apresente na tela:
a) a soma dos elementos abaixo da diagonal principal;
b) os elementos da diagonal principal.

14. Escreva um procedimento que preencha uma matriz M5×5. Desenvolva funções (uma para
cada opção abaixo), que recebam a matriz preenchida, calcule e retorne as informações a
seguir:
a) Soma da linha 4 de M;
b) Soma da coluna 2 de M;
c) Soma da diagonal principal;
d) Soma da diagonal secundária;
e) Soma de todos os elementos da matriz.
#
