import java.util.Scanner;

public class SeleçãoDeBandeira {

    /**
     * Identifica a bandeira de um cartão de crédito com base no número do cartão.
     *
     * @param numeroCartao O número do cartão de crédito como uma String.
     * @return A bandeira do cartão (ex.: Visa, MasterCard, etc.) ou "Bandeira desconhecida" se não for reconhecida.
     */
    public static String identificarBandeira(String numeroCartao) {
        if (numeroCartao.startsWith("4")) {
            return "Visa";
        } else if (numeroCartao.startsWith("5")) {
            return "MasterCard";
        } else if (numeroCartao.startsWith("3") && (numeroCartao.charAt(1) == '4' || numeroCartao.charAt(1) == '7')) {
            return "American Express";
        } else if (numeroCartao.startsWith("6")) {
            return "Discover";
        } else {
            return "Bandeira desconhecida";
        }
    }

    /**
     * Método principal para testar a identificação da bandeira do cartão.
     *
     * @param args Argumentos da linha de comando (não utilizados neste exemplo).
     */
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        while (true) {
            // Solicita ao usuário que insira o número do cartão
            System.out.print("Digite o número do cartão de crédito (16 dígitos) ou 'sair' para encerrar: ");
            String numeroCartao = scanner.nextLine();

            // Verifica se o usuário deseja encerrar o programa
            if (numeroCartao.equalsIgnoreCase("sair")) {
                System.out.println("Encerrando o programa...");
                break;
            }

            // Valida se o número do cartão contém exatamente 16 dígitos
            if (numeroCartao.length() != 16 || !numeroCartao.matches("\\d+")) {
                System.out.println("Número inválido! Certifique-se de digitar exatamente 16 dígitos.");
                continue;
            }

            // Identifica a bandeira do cartão
            String bandeira = identificarBandeira(numeroCartao);

            // Exibe a bandeira identificada no console
            System.out.println("A bandeira do cartão é: " + bandeira);
        }

        scanner.close();
    }
}
<!---
AdrielBatista11/AdrielBatista11 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
