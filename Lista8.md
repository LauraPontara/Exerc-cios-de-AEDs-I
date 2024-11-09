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
