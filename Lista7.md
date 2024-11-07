1. Resolução:
2. Resolução:
3. Resolução:
4. Resolução:
5. Resolução:
```c
#include <stdio.h>

void copiaNegativos(int vetor[], int length, int vetorNeg[])
{
    int pos = 0;
    for(int p = 0; p < length; p++)
    {
        if(vetor[p] < 0)
        {
            vetorNeg[pos] = vetor[p];
            pos++;
        }
    }

    // Preenche o restante do vetorNeg com zeros se houver menos que 10 elementos negativos
    while(pos < 10)
    {
        vetorNeg[pos] = 0;
        pos++;
    }

    printf("\nVetor Negativos com zeros: \n");
    for(int i = 0; i < 10; i++)
    {
        printf("%d ", vetorNeg[i]);
    }

    printf("\nVetor Negativos sem zeros: \n");
    for(int i = 0; i < 10; i++)
    {
        if(vetorNeg[i] != 0)
        {
            printf("%d ", vetorNeg[i]);
        }
    }
}

void preencheValores(int vetor[], int length)
{
    for(int i = 0; i < length; i++)
    {
        printf("Digite um valor: \n");
        scanf("%d", &vetor[i]);
    }

    printf("Vetor X preenchido: \n");
    for(int i = 0; i < length; i++)
    {
        printf("%d ", vetor[i]);
    }
}

int main(void)
{
    int X[10], tamanho = 10, vetorNeg[10];

    preencheValores(X, tamanho);

    copiaNegativos(X, tamanho, vetorNeg);

    return 0;
}
```


6. Resolução:
7. Resolução:
8. Resolução:
  ```c
#include <stdio.h>

int main()
{
    int A[10] = {1,2,3,4,5,6,7,8,9,0}, B[10], C[10];

    printf("Vetor A: \n");
    for(int i = 0; i < 10; i++)
    {
        printf("%d ", A[i]);
    }

    for(int j = 0; j < 10; j++)
    {
        printf("\nDigite um valor: \n");
        scanf("%d", &B[j]);

        if(B[j] == A[j])
        {
            do
            {
                if(B[j] == A[j])
                {
                    printf("Digite outro numero: \n");
                    scanf("%d", &B[j]);
                }

            }
            while(B[j] == A[j]);
        }
    }

    printf("Vetor B: \n");
    for(int i = 0; i <10; i++){
        printf("%d ", B[i]);
    }

    printf("Vetor A - B: \n");
    for(int i = 0; i < 10; i++){
        C[i] = A[i] - B[i];
        printf("%d ", C[i]);
    }
    return 0;
}
```

9. Resolução:
 ```c
    #include <stdio.h>

    int main(){
    int Idades[60], idade = 0, contaluno = 0;
    float media = 0, soma = 0;

    do{
        printf("Digite a idade do aluno: \n");
        scanf("%d", &idade);
        if(idade > 0){
            Idades[contaluno] = idade;
            soma += idade;
            contaluno++;
        }
    }while(idade > 0 && contaluno < 60);

    media = soma/contaluno;

    printf("Idades digitadas:\n");
    for(int i = 0; i < contaluno; i++){
        printf("%d ", Idades[i]);
    }

    printf("\nMedia das idades: %.1f\n", media);
    printf("Idades acima da media:\n");

    for(int i = 0; i < contaluno; i++){
        if(Idades[i] > media){
            printf("%d ", Idades[i]);
        }
    }
    return 0;
    }    


11. 
