import java.util.Scanner;
import java.util.Locale;

public class BancoAzul {
    public static void main(String[] args) {
        Locale.setDefault(Locale.US); 
        Scanner scanner = new Scanner(System.in);

        double saldo = 0;
        String extrato = "";
        int numeroSaques = 0;
        int LIMITE_SAQUES = 3;
        double LIMITE_VALOR_SAQUE = 500.00;

        while (true) {
            System.out.println("======================");
            System.out.println("Selecione uma opção:");
            System.out.println("[d] - Depósito");
            System.out.println("[s] - Saque");
            System.out.println("[e] - Extrato");
            System.out.println("[q] - Sair");
            System.out.println("======================");

            String menu = scanner.nextLine().toLowerCase();

            switch (menu) {
                case "d":
                    System.out.print("Informe o valor do depósito: R$ ");
                    double deposito = scanner.nextDouble();
                    scanner.nextLine();

                    if (deposito > 0) {
                        saldo += deposito;
                        extrato += String.format("Depósito: R$ %.2f\n", deposito);
                        System.out.printf("Depósito de R$ %.2f realizado com sucesso.%n", deposito);
                    } else {
                        System.out.println("Valor inválido para depósito.");
                    }
                    break;

                case "s":
                    if (numeroSaques >= LIMITE_SAQUES) {
                        System.out.println("Limite de saques diários atingido.");
                        break;
                    }

                    System.out.print("Informe o valor do saque: R$ ");
                    double saque = scanner.nextDouble();
                    scanner.nextLine(); 

                    if (saque <= 0) {
                        System.out.println("Valor insuficiente para o saque.");
                    } else if (saque > saldo) {
                        System.out.println("Saldo insuficiente para saque.");
                    } else if (saque > LIMITE_VALOR_SAQUE) {
                        System.out.println("O valor do saque excede o limite de R$ 500.00 por saque.");
                    } else {
                        saldo -= saque;
                        numeroSaques++;
                        extrato += String.format("Saque:    R$ %.2f\n", saque);
                        System.out.printf("Saque de R$ %.2f realizado com sucesso.%n", saque);
                    }
                    break;

                case "e":
                    System.out.println("===== EXTRATO =====");
                        if (extrato.equals("")) {
                        System.out.println("Não foram realizadas movimentações.");
                   
                    } else {
                        System.out.print(extrato);
                    }
                    System.out.printf("Saldo atual: R$ %.2f%n", saldo);
                    break;

                case "q":
                    System.out.println("Obrigado por usar o BancoAzul. Até logo!");
                    scanner.close();
                    return;
                    
                default:
                    System.out.println("Opção inválida. Tente novamente.");
            }
        }
    }
}
// Extrato
// Listar todas as movimentações (depósitos e saques) feitas.
// No final da listagem, mostrar o saldo atual.
// Formatar os valores no padrão brasileiro:   
// Ex: R$ 1500.45   
// Se não houver movimentações, mostrar:  
//Não foram realizadas movimentações.

//  Deposito 
//  Deve aceitar apenas valores positivos.
//  Todos os depósitos devem ser armazenados em memória.
//  O sistema considera apenas um único usuário (sem necessidade de autenticação ou identificação de conta).
//  Os depósitos devem aparecer no extrato.

// Saque 
// Permitir no máximo 3 saques diários.
// Cada saque pode ter o valor máximo de R$ 500,00.
// O sistema deve bloquear saques se o usuário não tiver saldo suficiente, exibindo mensagem:   
// Saldo insuficiente para saque. 
// Os saques devem ser armazenados e aparecer no extrato.
