#include <stdio.h>
#include <string.h>
#include <stdbool.h>

int main(void) {
    // Variáveis para as cartas
    char estado1[2], estado2[2];
    char codigo1[3], codigo2[3];
    char cidade1[30], cidade2[30];
    int populacao1, populacao2;
    float area1, area2;
    float PIB1, PIB2;
    float Denspop1, Denspop2;
    float PibC1, PibC2;
    int Pturisticos1, Pturisticos2;
    int opcao, atributo1 = 0, atributo2 = 0;
    int c;
    bool atributos_validos;

    // Registro dos dados da primeira carta
    printf("Digite a cidade do primeiro estado: ");
    fgets(cidade1, 30, stdin);
    cidade1[strcspn(cidade1, "\n")] = '\0';
    
    printf("Digite a letra do primeiro estado (A-H): ");
    scanf(" %s", estado1);
    while ((c = getchar()) != '\n' && c != EOF);
    
    printf("Digite o código do primeiro estado (ex: A01): ");
    scanf(" %s", codigo1);
    while ((c = getchar()) != '\n' && c != EOF);
    
    printf("Digite a população do primeiro estado: ");
    scanf(" %d", &populacao1);
    while ((c = getchar()) != '\n' && c != EOF);
    
    printf("Digite a área do primeiro estado (km²): ");
    scanf(" %f", &area1);
    while ((c = getchar()) != '\n' && c != EOF);
    
    printf("Digite o PIB do primeiro estado: ");
    scanf(" %f", &PIB1);
    while ((c = getchar()) != '\n' && c != EOF);
    
    printf("Digite o número de pontos turísticos do primeiro estado: ");
    scanf(" %d", &Pturisticos1);
    while ((c = getchar()) != '\n' && c != EOF);
    
    Denspop1 = populacao1 / area1;
    PibC1 = PIB1 / populacao1;

    // Registro dos dados da segunda carta
    printf("Digite a cidade do segundo estado: ");
    while ((c = getchar()) != '\n' && c != EOF);
    fgets(cidade2, 30, stdin);
    cidade2[strcspn(cidade2, "\n")] = '\0';
    
    printf("Digite a letra do segundo estado (A-H): ");
    scanf(" %s", estado2);
    while ((c = getchar()) != '\n' && c != EOF);
    
    printf("Digite o código do segundo estado (ex: B02): ");
    scanf(" %s", codigo2);
    while ((c = getchar()) != '\n' && c != EOF);
    
    printf("Digite a população do segundo estado: ");
    scanf(" %d", &populacao2);
    while ((c = getchar()) != '\n' && c != EOF);
    
    printf("Digite a área do segundo estado (km²): ");
    scanf(" %f", &area2);
    while ((c = getchar()) != '\n' && c != EOF);
    
    printf("Digite o PIB do segundo estado: ");
    scanf(" %f", &PIB2);
    while ((c = getchar()) != '\n' && c != EOF);
    
    printf("Digite o número de pontos turísticos do segundo estado: ");
    scanf(" %d", &Pturisticos2);
    while ((c = getchar()) != '\n' && c != EOF);
    
    Denspop2 = populacao2 / area2;
    PibC2 = PIB2 / populacao2;

    // Menu principal
    do {
        printf("\n\n=== MENU PRINCIPAL ===\n");
        printf("1. Comparar usando dois atributos\n");
        printf("2. Mostrar dados completos das cartas\n");
        printf("0. Sair\n");
        printf("Escolha uma opção: ");
        scanf("%d", &opcao);

        if (opcao == 0) break;

        switch (opcao) {
            case 1: // Comparação com dois atributos
                atributos_validos = false;
                while (!atributos_validos) {
                    // Menu para escolha do primeiro atributo
                    printf("\n=== ESCOLHA O PRIMEIRO ATRIBUTO ===\n");
                    printf("1. População\n");
                    printf("2. Área\n");
                    printf("3. PIB\n");
                    printf("4. Pontos Turísticos\n");
                    printf("5. Densidade Demográfica\n");
                    printf("Escolha o primeiro atributo: ");
                    scanf("%d", &atributo1);

                    if (atributo1 < 1 || atributo1 > 5) {
                        printf("Opção inválida! Tente novamente.\n");
                        continue;
                    }

                    // Menu dinâmico para escolha do segundo atributo
                    printf("\n=== ESCOLHA O SEGUNDO ATRIBUTO ===\n");
                    for (int i = 1; i <= 5; i++) {
                        if (i != atributo1) {
                            switch (i) {
                                case 1: printf("%d. População\n", i); break;
                                case 2: printf("%d. Área\n", i); break;
                                case 3: printf("%d. PIB\n", i); break;
                                case 4: printf("%d. Pontos Turísticos\n", i); break;
                                case 5: printf("%d. Densidade Demográfica\n", i); break;
                            }
                        }
                    }
                    printf("Escolha o segundo atributo (diferente do primeiro): ");
                    scanf("%d", &atributo2);

                    if (atributo2 == atributo1) {
                        printf("Você não pode escolher o mesmo atributo duas vezes!\n");
                    } else if (atributo2 < 1 || atributo2 > 5) {
                        printf("Opção inválida! Tente novamente.\n");
                    } else {
                        atributos_validos = true;
                    }
                }

                // Variáveis para armazenar os valores comparados
                float valor1_attr1, valor2_attr1;
                float valor1_attr2, valor2_attr2;
                char nome_attr1[30], nome_attr2[30];
                int pontos1 = 0, pontos2 = 0;
                float soma1 = 0, soma2 = 0;

                // Processamento do primeiro atributo
                switch (atributo1) {
                    case 1: // População
                        strcpy(nome_attr1, "População");
                        valor1_attr1 = populacao1;
                        valor2_attr1 = populacao2;
                        if (populacao1 > populacao2) pontos1++;
                        else if (populacao2 > populacao1) pontos2++;
                        soma1 += populacao1;
                        soma2 += populacao2;
                        break;
                    case 2: // Área
                        strcpy(nome_attr1, "Área");
                        valor1_attr1 = area1;
                        valor2_attr1 = area2;
                        if (area1 > area2) pontos1++;
                        else if (area2 > area1) pontos2++;
                        soma1 += area1;
                        soma2 += area2;
                        break;
                    case 3: // PIB
                        strcpy(nome_attr1, "PIB");
                        valor1_attr1 = PIB1;
                        valor2_attr1 = PIB2;
                        if (PIB1 > PIB2) pontos1++;
                        else if (PIB2 > PIB1) pontos2++;
                        soma1 += PIB1;
                        soma2 += PIB2;
                        break;
                    case 4: // Pontos Turísticos
                        strcpy(nome_attr1, "Pontos Turísticos");
                        valor1_attr1 = Pturisticos1;
                        valor2_attr1 = Pturisticos2;
                        if (Pturisticos1 > Pturisticos2) pontos1++;
                        else if (Pturisticos2 > Pturisticos1) pontos2++;
                        soma1 += Pturisticos1;
                        soma2 += Pturisticos2;
                        break;
                    case 5: // Densidade Demográfica (regra invertida)
                        strcpy(nome_attr1, "Densidade Demográfica");
                        valor1_attr1 = Denspop1;
                        valor2_attr1 = Denspop2;
                        if (Denspop1 < Denspop2) pontos1++;
                        else if (Denspop2 < Denspop1) pontos2++;
                        // Para a soma, usamos o valor normal (não invertido)
                        soma1 += 1/Denspop1; // Invertemos para manter a lógica de maior ser melhor
                        soma2 += 1/Denspop2;
                        break;
                }

                // Processamento do segundo atributo
                switch (atributo2) {
                    case 1: // População
                        strcpy(nome_attr2, "População");
                        valor1_attr2 = populacao1;
                        valor2_attr2 = populacao2;
                        if (populacao1 > populacao2) pontos1++;
                        else if (populacao2 > populacao1) pontos2++;
                        soma1 += populacao1;
                        soma2 += populacao2;
                        break;
                    case 2: // Área
                        strcpy(nome_attr2, "Área");
                        valor1_attr2 = area1;
                        valor2_attr2 = area2;
                        if (area1 > area2) pontos1++;
                        else if (area2 > area1) pontos2++;
                        soma1 += area1;
                        soma2 += area2;
                        break;
                    case 3: // PIB
                        strcpy(nome_attr2, "PIB");
                        valor1_attr2 = PIB1;
                        valor2_attr2 = PIB2;
                        if (PIB1 > PIB2) pontos1++;
                        else if (PIB2 > PIB1) pontos2++;
                        soma1 += PIB1;
                        soma2 += PIB2;
                        break;
                    case 4: // Pontos Turísticos
                        strcpy(nome_attr2, "Pontos Turísticos");
                        valor1_attr2 = Pturisticos1;
                        valor2_attr2 = Pturisticos2;
                        if (Pturisticos1 > Pturisticos2) pontos1++;
                        else if (Pturisticos2 > Pturisticos1) pontos2++;
                        soma1 += Pturisticos1;
                        soma2 += Pturisticos2;
                        break;
                    case 5: // Densidade Demográfica (regra invertida)
                        strcpy(nome_attr2, "Densidade Demográfica");
                        valor1_attr2 = Denspop1;
                        valor2_attr2 = Denspop2;
                        if (Denspop1 < Denspop2) pontos1++;
                        else if (Denspop2 < Denspop1) pontos2++;
                        // Para a soma, usamos o valor normal (não invertido)
                        soma1 += 1/Denspop1;
                        soma2 += 1/Denspop2;
                        break;
                }

                // Exibição dos resultados
                printf("\n=== RESULTADO DA COMPARAÇÃO ===\n");
                printf("Cidades: %s vs %s\n", cidade1, cidade2);
                printf("\nAtributos comparados:\n");
                printf("1. %s\n", nome_attr1);
                printf("   %s: %.2f\n", cidade1, valor1_attr1);
                printf("   %s: %.2f\n", cidade2, valor2_attr1);
                printf("2. %s\n", nome_attr2);
                printf("   %s: %.2f\n", cidade1, valor1_attr2);
                printf("   %s: %.2f\n", cidade2, valor2_attr2);
                
                printf("\nPontuação por atributo:\n");
                printf("%s: %d ponto(s)\n", cidade1, pontos1);
                printf("%s: %d ponto(s)\n", cidade2, pontos2);
                
                printf("\nSoma dos atributos:\n");
                printf("%s: %.2f\n", cidade1, soma1);
                printf("%s: %.2f\n", cidade2, soma2);
                
                printf("\nRESULTADO FINAL: ");
                if (soma1 > soma2) {
                    printf("%s vence!\n", cidade1);
                } else if (soma2 > soma1) {
                    printf("%s vence!\n", cidade2);
                } else {
                    printf("Empate!\n");
                }
                break;
                
            case 2: // Mostrar dados completos das cartas
                printf("\n=== CARTA 1 ===\n");
                printf("Estado: %s\n", estado1);
                printf("Código: %s\n", codigo1);
                printf("Cidade: %s\n", cidade1);
                printf("População: %d habitantes\n", populacao1);
                printf("Área: %.2f km²\n", area1);
                printf("PIB: %.2f\n", PIB1);
                printf("PIB per capita: %.2f\n", PibC1);
                printf("Pontos turísticos: %d\n", Pturisticos1);
                printf("Densidade populacional: %.2f hab/km²\n", Denspop1);
                
                printf("\n=== CARTA 2 ===\n");
                printf("Estado: %s\n", estado2);
                printf("Código: %s\n", codigo2);
                printf("Cidade: %s\n", cidade2);
                printf("População: %d habitantes\n", populacao2);
                printf("Área: %.2f km²\n", area2);
                printf("PIB: %.2f\n", PIB2);
                printf("PIB per capita: %.2f\n", PibC2);
                printf("Pontos turísticos: %d\n", Pturisticos2);
                printf("Densidade populacional: %.2f hab/km²\n", Denspop2);
                break;
                
            default:
                printf("Opção inválida!\n");
        }
    } while (opcao != 0);

    return 0;
}
