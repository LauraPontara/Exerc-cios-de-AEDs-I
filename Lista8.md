1. Resolução:
```c
int main(void)
{
    char S[100], I[100];
    printf("Digite uma palavra:\n");
    scanf("%s", S); //Le a palavra digitada para a string
    int tamanho = strlen(S); //cria uma var que recebe o tamanho da string
    printf("A palavra digitada foi: %s\n", S);
    printf("Tamanho: %d\n", tamanho);
    for(int i = 0; i < tamanho; i++)  //preenche a string I invertendo a palavra
    {
        I[i] = S[tamanho - i - 1];
        /*
        A posição i na string I recebe o que está
        na ultima posição da string S
        SEM CONTAR A CARACTERE NULO \0
        */
    }
    I[tamanho] = '\0';
    printf("A palavra inversa eh: %s\n", I);

    return 0;
}
```

2. Resolução:

```c
#include <stdio.h>
#include <string.h>

int main()
{
    int k;
    char palavra[100], letraCript[100];

    printf("Digite um valor:\n");
    scanf("%d", &k);

    printf("Digite uma palavra:\n");
    scanf("%s", palavra);

    printf("Palavra criptografada: ");

    int tamanho = strlen(palavra);
    for(int i = 0; i < tamanho; i++)
    {
        letraCript[i] = (palavra[i] + k) % 255;
    }
    letraCript[tamanho] = '\0';

    printf("%s", letraCript);

    printf("\n");
    return 0;
}
```

3. Resolução:
```c
#include <stdio.h>
#include <string.h>

int main()
{
    int k;
    char palavra_cripto[100], palavraDescript[100];

    printf("Digite o valor da chave:\n");
    scanf("%d", &k);

    printf("Digite a palavra criptografada:\n");
    scanf("%99s", palavra_cripto);

    printf("Palavra decriptografada: ");

    for(int i = 0; i < strlen(palavra_cripto); i++)
    {
        palavraDescript[i] = (palavra_cripto[i] - k) % 255;
    }
    
    palavraDescript[strlen(palavra_cripto)]= '\0'; //Adiciona o ultimo termo nulo para evitar lixos após as posições preenchidas pela palavra

    printf("%s", palavraDescript);
    return 0;
}
````

4. Resolução:
```c
#include <stdio.h>
#include <string.h>

void Maiusculo(char palavra[])
{
    ;

    for (int i = 0; i < strlen(palavra); i++)
    {
        // Verifica se o caractere está entre 'a' e 'z' (códigos ASCII de 97 a 122)
        if (palavra[i] >= 'a' && palavra[i] <= 'z')
        {
            palavra[i] = palavra[i] - 32;
        }
    }
    printf("Palavra toda em MAIUSCULO:\n");
    printf("%s", palavra);
}


void Minusculo(char palavra[])
{
    for(int i = 0; i < strlen(palavra); i++)
    {
        if(palavra[i] >= 'A' && palavra[i] <= 'Z')
        {
            palavra[i] = palavra[i] + 32;
        }
    }
    printf("Palavra toda em MINUSCULO: \n");
    printf("%s", palavra);
}



int main()
{
    char cadeia[100], escolha[10];

    printf("Digite uma cadeia de caracteres:\n");
    scanf("%99s", cadeia);

    printf("Maiusculo ou Minusculo?\n");
    scanf("%s", escolha);

    if(strcmp(escolha, "Maiusculo") == 0)
    {
        Maiusculo(cadeia);
    }
    else if(strcmp(escolha, "Minusculo") == 0) //Função strcmp retorna 0 se as strings forem iguais 
    {
        Minusculo(cadeia);
    }else{
        printf("Digite uma opçao valida!\n");
    }
    return 0;
}
````
5. Resolução:
6. Resolução:
```c
#include <stdio.h>
#include <string.h>

int main()
{
    int cont = 0, j = 0;
    char cadeia1[100], cadeia2[100], inverte[100];

    printf("Digite uma frase ou palavra:\n");
    fgets(cadeia1, sizeof(cadeia1), stdin); //fgets le tudo até o enter, inclui o \n dentro da string

    // Remove o '\n' no final de cadeia1, se existir
    cadeia1[strcspn(cadeia1, "\n")] = '\0';

    /*
    strcspn é uma função da biblioteca <string.h> em C, que busca
    o primeiro caractere de uma string (str1) que coincide com
    qualquer caractere de outra string (str2) e retorna a posição
    (índice) desse caractere em str1. Se nenhum caractere
    coincidente for encontrado, ela retorna o comprimento de str1
    */

    for(int i = 0; i < strlen(cadeia1); i++)
    {
        if(cadeia1[i] == ' ' || cadeia1[i] == '\0')
        {
            cont++;
        }
        else
        {
            cadeia2[j] = cadeia1[i];
            j++;
        }
    }
    cadeia2[j] = '\0';

    for(int i = 0; i < strlen(cadeia2); i++)
    {
        inverte[i] = cadeia2[strlen(cadeia2)-i-1];
    }
    inverte[strlen(cadeia2)] = '\0';
    if(strcmp(cadeia2, inverte) == 0)
    {
        printf("%s eh um palindromo!\n", cadeia1);
    }
    else
    {
        printf("%s nao eh um palindromo!\n", cadeia1);
    }


    return 0;
}
```

7. Resolução:
```c
#include <stdio.h>

int main()
{
    float Notas[5][4], buffer = 0, mediaAlunos = 0, maior = 0;
    int alunoMaior = 0;

    for(int i = 0; i < 5; i++)
    {
        for(int j = 0; j < 4; j++)
        {
            if(j == 0) //Preenche a coluna das matrículas
            {
                printf("Digite a matrícula do aluno %d\n", i + 1);
                scanf("%f", &buffer);
                Notas[i][j] = buffer;
            }
            else if(j == 1) //Preenche as colunas das medias das provas
            {
                printf("Digite a media das provas do aluno\n");
                scanf("%f", &buffer);
                Notas[i][j] = buffer;
            }
            else if(j == 2) //Preenche a coluna das medias dos trabalhos
            {
                printf("Digite a media dos trabalhos:\n");
                scanf("%f", &buffer);
                Notas[i][j] = buffer;
            }
            else if(j == 3) //Preenche a coluna das Notas Finais 
            {
                Notas[i][j] = Notas[i][1] + Notas[i][2];
            }
        }
    }

    for(int i = 0; i < 5; i++)
    {
        for(int j = 0; j < 4; j++)
        {
            printf("%.1f  ", Notas[i][j]); //Imprime cada elemento da matriz
        }
        printf("\n"); //Quebra a linha quando termina de preencher a linha i
    }

    for(int i = 0; i < 5; i++)
    {
        mediaAlunos += Notas[i][3]; //Concatena as notas de todos os alunos 
        if(Notas[i][3] > maior) //Verifica todas as notas até encontrar a maior
        {
            maior = Notas[i][3]; //Armazena a maior nota
            alunoMaior = Notas[i][0]; //Armazena a matrícula do aluno com maior nota
        }
    }

    mediaAlunos = mediaAlunos/5; //Calculo da media dos alunos 
    printf("Aluno com maior nota: %d\n", alunoMaior);
    printf("Media das notas: %.2f\n", mediaAlunos);

    return 0;
}
````

8. Resolução:
```c
#include <stdio.h>

int main()
{
    // Declaração das variáveis
    int valor_inteiro;
    float valor_real;
    char caractere;

    // Declaração dos ponteiros
    int *ptr_inteiro = &valor_inteiro;
    float *ptr_real = &valor_real;
    char *ptr_caractere = &caractere;

    valor_inteiro = 10;
    valor_real = 1.5;
    caractere = 'L';

    // Exibe os endereços e conteúdos antes da alteração
    printf("\nAntes da alteracao:\n");
    printf("Valor inteiro: %d\n Valor real: %.2f\n Caractere: %c\n", valor_inteiro, valor_real, caractere);

    printf("Com ponteiros: \n x = %d\n y = %.2f\n z = %c\n", *ptr_inteiro, *ptr_real, *ptr_caractere);

    printf("Endereço das variáveis:\n x = %p\n y = %p\n z = %p\n", ptr_inteiro, ptr_real, ptr_caractere);
    printf("Endereço dos ponteiros das variaveis: \n *x = %p\n *y = %p\n *z = %p\n", &ptr_inteiro, &ptr_real, &ptr_caractere);

    // Solicita os valores novos para as variáveis
    printf("Digite um valor inteiro, um valor real e um caractere:\n");
    scanf("%d %f %c", ptr_inteiro, ptr_real, ptr_caractere); //Nao precisa de *

    printf("Ponteiro para inteiro: conteudo = %d, endereco = %p endereco do ponteiro = %p\n\n", *ptr_inteiro, ptr_inteiro, &ptr_inteiro);

    printf("Ponteiro para real: conteudo = %.2f, endereco = %p endereco do ponteiro = %p\n\n", *ptr_real, ptr_real,&ptr_real);

    printf("Ponteiro para caractere: conteudo = %c, endereco = %p endereco do ponteiro = %p\n\n", *ptr_caractere, ptr_caractere, &ptr_caractere);

    return 0;
}
````

9. Resolução:
```c
#include <stdio.h>

// Procedimento para calcular comprimento e área
void calcCircunferencia(float R, float *compr, float *area)
{
    float PI = 3.14;
    *compr = 2 * PI * R;      // Calcula o comprimento da circunferência
    *area = PI * R * R;        // Calcula a área da circunferência
}

int main()
{
    float raio, comprimento, area;
    float *Circun = &comprimento, *Area = &area;

    // Solicita o valor do raio ao usuário
    printf("Digite o valor do raio da circunferencia: ");
    scanf("%f", &raio);

    // Chama o procedimento para calcular comprimento e área
    calcCircunferencia(raio, Circun, Area);

    // Exibe os resultados
    printf("Comprimento da circunferencia: %.2f\n", *Circun);
    printf("Área da circunferencia: %.2f\n", *Area);

    return 0;
}
````

10. Resolução:

```c
#include <stdio.h>

void func(int *px, int *py) {
    px = py; //O ponteira px passará a apontar para o mesmo ENDEREÇO que py
    *py = (*py) * (*px); //O CONTEÚDO apontado pelo py será multiplicado por ele mesmo 
    *px = *px + 2; // O CONTEÚDO apontado por px (mesmo que apontado por py) será adicionado +2
}

int main() {
    int x, y;
    printf("Digite um valor para x:\n");
    scanf("%d", &x);
    printf("Digite um valor para y:\n");
    scanf("%d", &y);
    func(&x, &y); //Passa os endereçõs de x e y como parâmetros

    printf("x = %d, y = %d\n", x, y);
    /*Com x = 5 e y = 6:
        Retorna: x = 5 e y = 38(6*6 + 2);
    */

    return 0;
}
````

11. Resolução:
12. Resolução:
```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main()
{
    float **M; //Cria um ponteiro de um ponteiro para a matriz (bidimencional)
    int n = 0;

    printf("Digite a quantidade de colunas/linhas:\n");
    scanf("%d", &n);

    // Aloca um array de ponteiros para as linhas
    M = (float **)malloc(n * sizeof(float *));
    if (M == NULL) {
        printf("Erro ao alocar memória.\n");
        return 1;
    }

    // Aloca cada linha individualmente
    for (int i = 0; i < n; i++) {
        M[i] = (float *)malloc(n * sizeof(float));
        if (M[i] == NULL) {
            printf("Erro ao alocar memória.\n");
            return 1;
        }
    }

    srand(time(0));

    // Preenche a matriz com valores aleatórios e imprime
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) {
            M[i][j] = (rand()/100.0);
            printf("%.1f\t", M[i][j]);
        }
        printf("\n");
    }

    // Libera a memória de cada linha
    for (int i = 0; i < n; i++) {
        free(M[i]);
    }
    // Libera o array de ponteiros
    free(M);

    return 0;
}
````
13. Resolução:
```c
#include <stdio.h>

int main()
{
    int M[4][4], soma = 0;

    // Leitura dos elementos da matriz
    printf("Digite os elementos da matriz 4x4:\n");

    for (int i = 0; i < 4; i++)
    {
        for (int j = 0; j < 4; j++)
        {
            printf("M[%d][%d]: ", i, j);
            scanf("%d", &M[i][j]);
        }
    }

    // Exibe a matriz completa
    printf("\nMatriz 4x4:\n");
    for (int i = 0; i < 4; i++)
    {
        for (int j = 0; j < 4; j++)
        {
            printf("%d\t", M[i][j]);
        }
        printf("\n");
    }

    // Calcula a soma dos elementos abaixo da diagonal principal e mostra a diagonal principal
       printf("Diagonal Principal:\n");
    for (int i = 0; i < 4; i++)
    {
        for (int j = 0; j < 4; j++)
        {
            if(i == j)
            {
                printf("%d\n", M[i][j]);
            }
            else if (i > j)
            {
                soma += M[i][j];
            }
        }
    }
````
14. Resolução:
```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

// Procedimento para preencher a matriz 5x5 automaticamente e imprimir
void preencherMatriz(int M[5][5])
{
    // Inicializar a semente para números aleatórios
    srand(time(0));

    // Preencher a matriz com valores aleatórios entre 1 e 100
    for (int i = 0; i < 5; i++)
    {
        for (int j = 0; j < 5; j++)
        {
            M[i][j] = rand() % 100 + 1;
        }
    }

    // Exibir a matriz completa
    printf("Matriz 5x5:\n");
    for (int i = 0; i < 5; i++)
    {
        for (int j = 0; j < 5; j++)
        {
            printf("%d\t", M[i][j]);
        }
        printf("\n");
    }
}

// Funções de soma específicas
int somaLinha4(int M[5][5])
{
    int soma = 0;
    for (int j = 0; j < 5; j++)
    {
        soma += M[4][j];
    }
    return soma;
}

int somaColuna2(int M[5][5])
{
    int soma = 0;
    for (int i = 0; i < 5; i++)
    {
        soma += M[i][2];
    }
    return soma;
}

int somaDiagonalPrincipal(int M[5][5])
{
    int soma = 0;
    for (int i = 0; i < 5; i++)
    {
        soma += M[i][i]; //Elementos da diagonal principal tem sua linha e coluna iguais
    }
    return soma;
}

int somaDiagonalSecundaria(int M[5][5])
{
    int soma = 0;
    for (int i = 0; i < 5; i++)
    {
        for(int j = 0; j < 5; j++){
            if( i + j == 4){
/*Elementos da diagonal secundária tem a soma de sua linha + coluna igual
a quantidade de linhas ou colunas da matriz - 1 (5 - 1 = 4 nesse caso)*/
                soma += M[i][j];
            }
        }
    }
    return soma;
}

int somaTodosElementos(int M[5][5])
{
    int soma = 0;
    for (int i = 0; i < 5; i++)
    {
        for (int j = 0; j < 5; j++)
        {
            soma += M[i][j];
        }
    }
    return soma;
}

int main()
{
    int M[5][5];

    // Preenche e exibe a matriz
    preencherMatriz(M);

    // Calcula e exibe as somas requisitadas
    printf("\nSoma da linha 4: %d\n", somaLinha4(M));
    printf("Soma da coluna 2: %d\n", somaColuna2(M));
    printf("Soma da diagonal principal: %d\n", somaDiagonalPrincipal(M));
    printf("Soma da diagonal secundaria: %d\n", somaDiagonalSecundaria(M));
    printf("Soma de todos os elementos da matriz: %d\n", somaTodosElementos(M));

    return 0;
}
````
