# C-productions
Aqui eu coloco aquilo que eu faço utilizando a linguagem C.

## 📚 Atividades realizadas na graduação UFU

Abaixo estão os scripts com base nas aulas das atividades para a realização na linguagem C.
<details>
<summary><b> 📜 Estudos </b></summary>

<details style="margin-left: 20px;">
<summary> Lista de exercícios </summary>

```r
#include <stdio.h>

#include <stdlib.h>



// =========================================================

// FUNÇÕES DOS EXERCÍCIOS

// =========================================================



// --- Exercício 1 ---

void exercicio_01() {

    printf("\n--- 1) Lista C02 Exercicio 11 ---\n");

    int num, soma = 0;

    while (1) {

        printf("Digite um numero inteiro (ou 0 para sair): ");

        scanf("%d", &num);

        if (num == 0) break;

        if (num < 0) {

            printf("Numero invalido. Digite novamente.\n");

            continue;

        }

        int temp = num;

        soma = 0; // Reseta a soma para cada novo numero

        while (temp > 0) {

            soma += temp % 10;

            temp /= 10;

        }

        printf("A soma dos algarismos do numero e: %d\n\n", soma);

    }

}



// --- Exercício 2 ---

void exercicio_02() {

    printf("\n--- 2) Lista C02 Exercicio 18 ---\n");

    int opcao;

    double num1, num2, resultado;

    do {

        printf("\nMenu de operacoes matematicas:\n");

        printf("1. Soma\n2. Subtracao\n3. Multiplicacao\n4. Divisao\n5. Voltar ao menu principal\n");

        printf("Digite a opcao desejada: ");

        scanf("%d", &opcao);



        if (opcao >= 1 && opcao <= 4) {

            printf("Digite os dois numeros: ");

            scanf("%lf %lf", &num1, &num2);

        }



        switch (opcao) {

            case 1:

                resultado = num1 + num2;

                printf("Resultado: %.2lf\n", resultado);

                break;

            case 2:

                resultado = num1 - num2;

                printf("Resultado: %.2lf\n", resultado);

                break;

            case 3:

                resultado = num1 * num2;

                printf("Resultado: %.2lf\n", resultado);

                break;

            case 4:

                if (num2 == 0) {

                    printf("Erro: divisao por zero.\n");

                } else {

                    resultado = num1 / num2;

                    printf("Resultado: %.2lf\n", resultado);

                }

                break;

            case 5:

                printf("Saindo da calculadora...\n");

                break;

            default:

                printf("Opcao invalida. Digite novamente.\n");

                break;

        }

    } while (opcao != 5);

}



// --- Exercício 3 ---

void exercicio_03() {

    printf("\n--- 3) Lista C02 Exercicio 30 ---\n");

    int num1, num2, num3;

    printf("Digite o primeiro numero: "); scanf("%d", &num1);

    printf("Digite o segundo numero: "); scanf("%d", &num2);

    printf("Digite o terceiro numero: "); scanf("%d", &num3);



    if (num1 > num2) { int temp = num1; num1 = num2; num2 = temp; }

    if (num2 > num3) { int temp = num2; num2 = num3; num3 = temp; }

    if (num1 > num2) { int temp = num1; num1 = num2; num2 = temp; }



    printf("Os numeros em ordem crescente sao: %d, %d, %d\n", num1, num2, num3);

}



// --- Exercício 4 ---

void exercicio_04() {

    printf("\n--- 4) Lista C03 Exercicio 8 ---\n");

    int num, menor = 0, maior = 0;

    for (int i = 0; i < 10; i++) {

        printf("Digite o %do numero: ", i + 1);

        scanf("%d", &num);

        if (i == 0) {

            menor = num;

            maior = num;

        } else {

            if (num < menor) menor = num;

            if (num > maior) maior = num;

        }

    }

    printf("O menor numero lido foi: %d\n", menor);

    printf("O maior numero lido foi: %d\n", maior);

}



// --- Exercício 5 ---

void exercicio_05() {

    printf("\n--- 5) Lista C03 Exercicio 18 ---\n");

    int N, num, maior = 0, cont = 0;

    printf("Digite a quantidade de numeros: ");

    scanf("%d", &N);



    for (int i = 0; i < N; i++) {

        printf("Digite o %do numero: ", i + 1);

        scanf("%d", &num);

        if (i == 0 || num > maior) {

            maior = num;

            cont = 1;

        } else if (num == maior) {

            cont++;

        }

    }

    printf("O maior numero lido foi: %d\n", maior);

    printf("A quantidade de vezes que ele apareceu e: %d\n", cont);

}



// --- Exercício 6 ---

void exercicio_06() {

    printf("\n--- 6) Lista C03 Exercicio 21 ---\n");

    int num1, num2;

    double somaPares = 0.0, produtoImpares = 1.0;

    printf("Digite o primeiro numero: "); scanf("%d", &num1);

    printf("Digite o segundo numero: "); scanf("%d", &num2);



    if (num1 > num2) { int temp = num1; num1 = num2; num2 = temp; }



    for (int i = num1; i <= num2; i++) {

        if (i % 2 == 0) {

            somaPares += i;

        } else {

            produtoImpares *= i;

        }

    }

    printf("A soma dos numeros pares do intervalo e: %.2lf\n", somaPares);

    printf("O produto dos numeros impares do intervalo e: %.2lf\n", produtoImpares);

}



// --- Função Auxiliar para o Exercício 7 ---

int isPrime(int num) {

    if (num <= 1) return 0;

    for (int i = 2; i * i <= num; i++) {

        if (num % i == 0) return 0;

    }

    return 1;

}



// --- Exercício 7 ---

void exercicio_07() {

    printf("\n--- 7) Lista C03 Exercicio 54 ---\n");

    int num;

    printf("Digite um numero inteiro maior que 1: ");

    scanf("%d", &num);

    if (isPrime(num)) {

        printf("%d e primo.\n", num);

    } else {

        printf("%d nao e primo.\n", num);

    }

}



// --- Exercício 8 ---

void exercicio_08() {

    printf("\n--- 8) Lista C04 Exercicio 6 ---\n");

    int vetor[10], maior, menor;

    for (int i = 0; i < 10; i++) {

        printf("Digite o elemento %d do vetor: ", i + 1);

        scanf("%d", &vetor[i]);

    }

    maior = vetor[0];

    menor = vetor[0];

    for (int i = 1; i < 10; i++) {

        if (vetor[i] > maior) maior = vetor[i];

        if (vetor[i] < menor) menor = vetor[i];

    }

    printf("Maior elemento: %d\n", maior);

    printf("Menor elemento: %d\n", menor);

}



// --- Exercício 9 ---

void exercicio_09() {

    printf("\n--- 9) Lista C04 Exercicio 7 ---\n");

    int vetor[10], maior, posicaoMaior = 0;

    for (int i = 0; i < 10; i++) {

        printf("Digite o elemento %d do vetor: ", i + 1);

        scanf("%d", &vetor[i]);

    }

    maior = vetor[0];

    for (int i = 1; i < 10; i++) {

        if (vetor[i] > maior) {

            maior = vetor[i];

            posicaoMaior = i;

        }

    }

    printf("Vetor: ");

    for (int i = 0; i < 10; i++) {

        printf("%d ", vetor[i]);

    }

    printf("\nMaior elemento: %d\n", maior);

    printf("Posicao do maior elemento: %d\n", posicaoMaior + 1);

}



// --- Exercício 10 ---

void exercicio_10() {

    printf("\n--- 10) Lista C04 Exercicio 11 ---\n");

    double vetor[10], somaPositivos = 0.0;

    int quantidadeNegativos = 0;

    for (int i = 0; i < 10; i++) {

        printf("Digite o elemento %d do vetor: ", i + 1);

        scanf("%lf", &vetor[i]);

    }

    for (int i = 0; i < 10; i++) {

        if (vetor[i] < 0) {

            quantidadeNegativos++;

        } else if (vetor[i] > 0) {

            somaPositivos += vetor[i];

        }

    }

    printf("Quantidade de numeros negativos: %d\n", quantidadeNegativos);

    printf("Soma dos numeros positivos: %.2lf\n", somaPositivos);

}





// =========================================================

// FUNÇÃO PRINCIPAL (MENU)

// =========================================================

int main() {

    int opcao;



    do {

        printf("\n========================================\n");

        printf("          MENU - TRABALHO 03            \n");

        printf("========================================\n");

        printf("1. Exercicio 01 (Lista C02 - Ex 11)\n");

        printf("2. Exercicio 02 (Lista C02 - Ex 18)\n");

        printf("3. Exercicio 03 (Lista C02 - Ex 30)\n");

        printf("4. Exercicio 04 (Lista C03 - Ex 08)\n");

        printf("5. Exercicio 05 (Lista C03 - Ex 18)\n");

        printf("6. Exercicio 06 (Lista C03 - Ex 21)\n");

        printf("7. Exercicio 07 (Lista C03 - Ex 54)\n");

        printf("8. Exercicio 08 (Lista C04 - Ex 06)\n");

        printf("9. Exercicio 09 (Lista C04 - Ex 07)\n");

        printf("10. Exercicio 10 (Lista C04 - Ex 11)\n");

        printf("0. Sair\n");

        printf("========================================\n");

        printf("Escolha qual exercicio deseja rodar: ");

        scanf("%d", &opcao);



        switch(opcao) {

            case 1: exercicio_01(); break;

            case 2: exercicio_02(); break;

            case 3: exercicio_03(); break;

            case 4: exercicio_04(); break;

            case 5: exercicio_05(); break;

            case 6: exercicio_06(); break;

            case 7: exercicio_07(); break;

            case 8: exercicio_08(); break;

            case 9: exercicio_09(); break;

            case 10: exercicio_10(); break;

            case 0: printf("\nSaindo do programa... Ate logo!\n"); break;

            default: printf("\nOpcao invalida! Tente novamente.\n");

        }

    } while (opcao != 0);



    return 0;

}

```


