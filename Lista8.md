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
