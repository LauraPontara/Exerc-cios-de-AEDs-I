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
## Questão 4

```c++
#include <iostream>
#include <string>

using namespace std;

class ContaCorrente
{
protected:
    float saldo;
public:
    ContaCorrente()
    {
        saldo = 0;
    }

    void depositar(float valor)
    {
        saldo += valor;
    }

    virtual void sacar(float valor)
    {
        if((valor + (valor*0.005))<= saldo)
        {
            saldo -= (valor + (valor*0.005));
        }
        else
        {
            cout << "Saldo insuficiente" << endl;
        }
    }

    float getSaldo()
    {
        return saldo;
    }

};

class ContaEspecial : public ContaCorrente
{
public:
    ContaEspecial(): ContaCorrente() {}

    void sacar(float valor) override
    {
        if((valor+(valor*0.001))<= saldo)
        {
            saldo -= (valor+(valor*0.001));
        }
        else
        {
            cout << "Saldo insuficiente" << endl;
        }
    }
};


int main()
{
    int escolha = 0;

    cout << "Escolha o tipo da conta: " << endl;
    cout << "1 - Comum" << endl;
    cout << "2 - Especial" << endl;
    cin >> escolha;

    switch(escolha)
    {
    case 1:
    {
        ContaCorrente NovaConta;
        int opcao = 0;
        do
        {
            cout << "O que deseja fazer?" << endl;
            cout << "1 - Depositar \n 2 - Sacar \n 3 - Ver saldo \n 4 - Sair" << endl;
            cin >> opcao;
            switch(opcao)
            {
            case 1:
            {
                float quantia;
                cout << "Quanto deseja depositar?" << endl;
                cin >> quantia;
                NovaConta.depositar(quantia);
            }
            break;
            case 2:
            {
                float quantia;
                cout << "Quanto deseja sacar?" << endl;
                cin >> quantia;
                NovaConta.sacar(quantia);
            }
            break;
            case 3:
                cout << "Saldo: " << NovaConta.getSaldo() << endl;
            break;

            default:
                cout << "Opção inválida"<< endl;
            }
        }
        while(opcao != 4);
    }
    break;
    case 2:
    {
        ContaEspecial NovaConta;
        int opcao = 0;
        do
        {
            cout << "O que deseja fazer?" << endl;
            cout << "1 - Depositar \n 2 - Sacar \n 3 - Ver saldo \n 4 - Sair" << endl;
            cin >> opcao;
            switch(opcao)
            {
            case 1:
            {
                float quantia;
                cout << "Quanto deseja depositar?" << endl;
                cin >> quantia;
                NovaConta.depositar(quantia);
            }
            break;
            case 2:
            {
                float quantia;
                cout << "Quanto deseja sacar?" << endl;
                cin >> quantia;
                NovaConta.sacar(quantia);
            }
            break;
            case 3:
                cout<< "Saldo: " << NovaConta.getSaldo() << endl;
            break;
            default:
                cout << "Opção inválida"<< endl;
            }
        }
        while(opcao != 4);
    }
    break;

    default:
        cout << "Escolha inválida" << endl;
    }


    return 0;
}
````
