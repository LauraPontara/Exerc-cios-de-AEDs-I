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
            if(j == 0)
            {
                printf("Digite a matrícula do aluno %d\n", i + 1);
                scanf("%f", &buffer);
                Notas[i][j] = buffer;
            }
            else if(j == 1)
            {
                printf("Digite a media das provas do aluno\n");
                scanf("%f", &buffer);
                Notas[i][j] = buffer;
            }
            else if(j == 2)
            {
                printf("Digite a media dos trabalhos:\n");
                scanf("%f", &buffer);
                Notas[i][j] = buffer;
            }
            else if(j == 3)
            {
                Notas[i][j] = Notas[i][1] + Notas[i][2];
            }
        }
    }

    for(int i = 0; i < 5; i++)
    {
        for(int j = 0; j < 4; j++)
        {
            printf("%.1f  ", Notas[i][j]);
        }
        printf("\n");
    }

    for(int i = 0; i < 5; i++)
    {
        mediaAlunos += Notas[i][3];
        if(Notas[i][3] > maior)
        {
            maior = Notas[i][3];
            alunoMaior = Notas[i][0];
        }
    }

    mediaAlunos = mediaAlunos/5;
    printf("Aluno com maior nota: %d\n", alunoMaior);
    printf("Media das notas: %.2f\n", mediaAlunos);

    return 0;
}
````
