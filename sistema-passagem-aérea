#include <stdio.h>  // Para usar printf e scanf

// Função para converter letra para maiúscula
char toUpperCase(char c) {
    if (c >= 'a' && c <= 'z') {
        return c - ('a' - 'A');  // Converte de minúscula para maiúscula
    }
    return c;
}

// Função para converter letra para minúscula
char toLowerCase(char c) {
    if (c >= 'A' && c <= 'Z') {
        return c + ('a' - 'A');  // Converte de maiúscula para minúscula
    }
    return c;
}

int main() {
    char reserva[10][6] = {
        {' ', ' ', ' ', ' ', ' ', ' '},
        {' ', ' ', ' ', ' ', ' ', ' '},
        {' ', ' ', ' ', ' ', ' ', ' '},
        {' ', ' ', ' ', ' ', ' ', ' '},
        {' ', ' ', ' ', ' ', ' ', ' '},
        {' ', ' ', ' ', ' ', ' ', ' '},
        {' ', ' ', ' ', ' ', ' ', ' '},
        {' ', ' ', ' ', ' ', ' ', ' '},
        {' ', ' ', ' ', ' ', ' ', ' '},
        {' ', ' ', ' ', ' ', ' ', ' '}
    };
    
    int fileira = -1, acento = -1;
    char poltrona = ' ';
    char tipoPassagem = ' ';
    char continuar = ' ';
    
    do {
        // Escolher tipo de passagem
        printf("\nEscolha o tipo de passagem (E para Executivo, C para Econômico): ");
        scanf(" %c", &tipoPassagem);
        tipoPassagem = toUpperCase(tipoPassagem);  // Converter para maiúscula

        // Escolher fileira e poltrona
        printf("\nDigite a fileira (1-10): ");
        scanf("%d", &fileira);

        printf("\nDigite a poltrona [A][B][C][D][E][F]: ");
        scanf(" %c", &poltrona);
        poltrona = toUpperCase(poltrona);  // Converter para maiúscula

        switch (poltrona) {
            case 'A':
                acento = 0;
                break;
            case 'B':
                acento = 1;
                break;
            case 'C':
                acento = 2;
                break;
            case 'D':
                acento = 3;
                break;
            case 'E':
                acento = 4;
                break;
            case 'F':
                acento = 5;
                break;
            default:
                printf("\nPoltrona invalida");
                continue;  // Voltar para o início do loop se a poltrona for inválida
        }

        // Verificar se o assento já está reservado
        if (reserva[fileira-1][acento] == 'x') {
            printf("\nEsse assento já está reservado. Por favor, escolha outro.\n");
            continue;  // Voltar ao início do loop para tentar outro assento
        }

        // Verificar regras de tipo de passagem
        if (tipoPassagem == 'C' && (poltrona == 'A' || poltrona == 'F')) {
            printf("\nAssentos A e F são exclusivos para a classe Executiva. Escolha outra poltrona.\n");
            continue;
        } else if (tipoPassagem == 'E' && (poltrona != 'A' && poltrona != 'F')) {
            printf("\nRecomendamos que passageiros Executivos escolham as poltronas A ou F.\n");
        }

        // Reservar o assento
        reserva[fileira-1][acento] = 'x';
        
        // Exibir mapa de assentos
        printf("\n\t\t[A] [B] [C]\t[D] [E] [F]\n");
        for (int x = 0; x < 10; x++) {
            if (x != 9) {
                printf("\n\t0%d\t", x + 1);
            } else {
                printf("\n\t%d\t", x + 1);
            }
            
            for (int y = 0; y < 6; y++) {
                printf("[%c] ", reserva[x][y]);
                if (y == 2) {
                    printf("\t");
                }
            }
        }
        printf("\n");

        // Perguntar se deseja continuar
        printf("\nDeseja realizar outra reserva? (S/N): ");
        scanf(" %c", &continuar);
        continuar = toLowerCase(continuar);  // Converter para minúscula
    } while (continuar == 's');

    printf("\nEncerrando o sistema de reservas...\n");

    return 0;
}
