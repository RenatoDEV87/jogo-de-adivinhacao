# Jogo de Adivinhação 🎯

Este é um programa simples que simula um **jogo de adivinhação** em Java. O objetivo é adivinhar um número gerado aleatoriamente entre 0 e 100, com um limite de até 5 tentativas. 

## Funcionamento do Programa

1. O programa gera um número aleatório entre 0 e 100.
2. O usuário tenta adivinhar o número, inserindo valores pelo terminal.
3. A cada tentativa, o programa informa se o número digitado é:
   - **Maior** ou **menor** do que o número gerado.
4. O jogo termina quando:
   - O usuário adivinha corretamente o número, ou
   - O limite de 5 tentativas é atingido.

## Tecnologias Utilizadas

- **Linguagem**: Java
- **Bibliotecas**: 
  - `java.util.Random` para gerar números aleatórios.
  - `java.util.Scanner` para leitura de entradas do usuário.

## Código Fonte

```java
import java.util.Random;
import java.util.Scanner;

public class JogoAdivinhacao {

    public static void main(String[] args) {
        Scanner leitor = new Scanner(System.in);
        int numeroGerado = new Random().nextInt(100); // gera um número aleatório entre 0 e 100
        int tentativas = 0;
        int numeroDigitado = 0;
        
        while (tentativas < 5) {
            System.out.print("Digite um número entre 0 e 100: ");
            numeroDigitado = leitor.nextInt();
            tentativas++;
            
            if (numeroDigitado == numeroGerado) {
                System.out.println("Parabéns, você acertou o número em " + tentativas + " tentativas!");
                break; // interrompe o loop while
            } else if (numeroDigitado < numeroGerado) {
                System.out.println("O número digitado é menor que o número gerado.");
            } else {
                System.out.println("O número digitado é maior que o número gerado.");
            }
        }

        if (tentativas == 5 && numeroDigitado != numeroGerado) {
             System.out.println("Você não conseguiu acertar o número em 05 tentativas. O número era: " + numeroGerado);
        }
    }
}
```

## Melhorias Futuras

1 - Adicionar diferentes níveis de dificuldade (com intervalos de números e número de tentativas).

2 - Implementar uma interface gráfica para o jogo.

3 - Permitir que o intervalo do número gerado seja configurável.

## Licença

Este projeto está sob a licença MIT. Consulte o arquivo LICENSE para mais detalhes.
