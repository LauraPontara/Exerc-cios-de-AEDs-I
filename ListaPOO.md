## Questão 3
```c++
#include <iostream>
#include <string>

using namespace std;

class Eletrodomestico
{
private:
    string loja;
    string telefone;
    float preco;

public:

    Eletrodomestico()
    {
        loja = " ";
        telefone = " ";
        preco = 0;

    }

    void setLoja(string loja)
    {
        this->loja = loja;
    }

    void setTelefone(string telefone)
    {
        this->telefone = telefone;
    }

    void setPreco(float p)
    {
        if(p > 0.0)
        {
            preco = p;
        }
        else
        {
            cout << "Preço inválido" <<endl;
        }
    }

    string getLoja()
    {
        return loja;
    }

    string getTelefone()
    {
        return telefone;
    }

    float getPreco()
    {
        return preco;
    }

    Eletrodomestico(string l, string t, float p)
    {
        setLoja(l);
        setTelefone(t);
        setPreco(p);
    }
};

int main()
{
    Eletrodomestico eletrodomesticos[15];

    for(int i = 0; i < 15; i++)
    {
        string loja, telefone;
        float preco;
        cout << "Eletrodomestico " << i+1<< endl;
        cout<< "Digite o nome da loja "<< endl;
        cin.ignore();
        getline(cin, loja);

        cout << "Digite o telefone" << endl;
        getline(cin, telefone);

        cout << "Digite o preço do eletrodomestico" << endl;
        cin >> preco;

        eletrodomesticos[i] = Eletrodomestico(loja, telefone, preco);
    }

    float menorPreco = eletrodomesticos[0].getPreco();
    float maiorPreco = eletrodomesticos[0].getPreco();
    int PosiMenor = 0, PosiMaior = 0;
    float somaPrecos = 0;

    for(int i = 0; i < 15; i++)
    {
        float precoEmAnalise = eletrodomesticos[i].getPreco();
        somaPrecos += precoEmAnalise;
        if(precoEmAnalise < menorPreco)
        {
            menorPreco = precoEmAnalise;
            PosiMenor = i;
        }
        if(precoEmAnalise > maiorPreco)
        {
            maiorPreco = precoEmAnalise;
            PosiMaior = i;
        }
    }

    float mediaPrecos = (somaPrecos/15);

    cout << "Média de preços: " << mediaPrecos << endl;
    cout << "Menor preço: " << menorPreco << endl;
    cout << "Loja do menor preço: " << eletrodomesticos[PosiMenor].getLoja() << endl;
    cout << "Maior preço: " << maiorPreco << endl;
    cout << "Loja do maior preço: " << eletrodomesticos[PosiMaior].getLoja() << endl;

    return 0;
}
````
