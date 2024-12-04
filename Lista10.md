## 1)
```c++
#include <iostream>
#include <string>

using namespace std;

class Cliente
{
private:
    string nome;
    int diaNasc;
    int mesNasc;
    int anoNasc;
    string telefone;
    string rua;
    string cidade;
    int num;

public:

    Cliente(){
        nome = " ";
        diaNasc = 0;
        mesNasc = 0;
        anoNasc = 0;
        telefone = " ";
        rua = " ";
        cidade = " ";
        num = 0;
    }
    Cliente(string nome, int diaNasc, int mesNasc, int anoNasc, string telefone, string rua, string cidade, int num)
    {
        this->nome = nome;
        this->diaNasc = diaNasc;
        this->mesNasc = mesNasc;
        this->anoNasc = anoNasc;
        this->telefone = telefone;
        this->rua = rua;
        this->cidade = cidade;
        this->num = num;
    }

    string getNome()
    {
        return nome;
    }
    int getDia()
    {
        return diaNasc;
    }
    int getMes()
    {
        return mesNasc;
    }
    int getAno()
    {
        return anoNasc;
    }
    string getTel()
    {
        return telefone;
    }
    string getRua()
    {
        return rua;
    }
    string getCidade()
    {
        return cidade;
    }
    int getNum()
    {
        return num;
    }
};


int main()
{
    int tamanho = 0, numCli = 0, dia = 0, mes = 0, ano = 0;
    string nome, cidade, rua, telefone;

    cout << "Quantos clientes deseja cadastrar?" << endl;
    cin >> tamanho;
    cin.ignore();
    Cliente clientes[tamanho];

    for(int i = 0; i < tamanho; i++)
    {
        cout << "Informe o nome do cliente " << i+1 << endl;
        getline(cin, nome);


        cout << "Informe a cidade do cliente:" << endl;
        getline(cin, cidade);

        cout << "Informe o telefone do cliente:" << endl;
        cin >> telefone;
        cin.ignore();
        cout << "Informe a rua onde o cliente mora:" << endl;
        getline(cin, rua);

        cout << "Digite o número residencial: " << endl;
        cin >> numCli;
        cin.ignore();
        cout << "Digite o dia, o mês e o ano de nascimento do cliente respectivamente: " << endl;
        cin >> dia >> mes >> ano;
        cin.ignore();
        clientes[i] = Cliente (nome, dia, mes,ano, telefone, rua, cidade, numCli);
    }

    for(int j = 0; j < tamanho; j++){
        cout << "\nCliente " << j + 1 << endl;
        cout << "Nome: " << clientes[j].getNome() << endl;
        cout << "Telefone: " << clientes[j].getTel() << endl;
        cout << "Data de Nascimento: " << clientes[j].getDia() << "/" << clientes[j].getMes() << "/" << clientes[j].getAno() << endl;
        cout << "Endereço: " << clientes[j].getRua() << ", nº" << clientes[j].getNum() << "-" << clientes[j].getCidade() << endl;
    }


    return 0;
}
````
