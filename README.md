<img width="639" height="289" alt="image" src="https://github.com/user-attachments/assets/e6c4be59-696e-42fa-b56d-16a2b2ea01d1" />


Uma exceção é um evento, normalmente associado a um erro, e que ao ser disparado interrompe o fluxo
normal de execução da aplicação






EXCEÇÃO PERSONALIZADA 

# P3-PM<img width="418" height="135" alt="m1" src="https://github.com/user-attachments/assets/98382cba-bc33-4cd6-91cb-3a2d48183b40" />






THROW 
<img width="372" height="42" alt="image" src="https://github.com/user-attachments/assets/c21fd798-4db4-41e2-89c7-9b3399b3502f" />
if (valor > saldo) {
      throw new SaldoInsuficienteException("Saldo insuficiente");
  } 








THROWS 
<img width="452" height="161" alt="image" src="https://github.com/user-attachments/assets/734ccb85-3607-4afb-8667-bf7c508f4069" />


import java.util.Scanner;

public class Main {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);
        Pessoa P = new Pessoa(0);

        try {
            System.out.print("Digite sua idade: ");
            int idade = sc.nextInt();
            P.setIdade(idade);

        } catch (MenorDeIdadeException e) {
            System.out.println(e.getMessage());
        }

       
    }
}



class Pessoa {

    private int idade;

    public int getIdade() {
        return idade;
    }

    public void setIdade(int idade) throws MenorDeIdadeException {
        if (idade < 18) {
            throw new MenorDeIdadeException("Erro");
        } else {
            this.idade = idade;
        }
    }

    Pessoa(int idade) {
        this.idade = idade;
    }
}


class MenorDeIdadeException extends Exception{
    
    public MenorDeIdadeException(String mensagem){
        super(mensagem);
    }
}




