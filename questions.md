- Questão 01
A saída é 91;

- Questão 02
#include <stdio.h>
int main(){
    int input, baseCase1 = 1, baseCase2 = 1, actual = 0; 
    printf("Digite um valor inteiro: ");
    scanf("%d", &input);
    actual = baseCase1 + baseCase2;
    if(((input == baseCase1) || (input == baseCase2) || (input == actual))){
        printf("Esse número faz parte da sequência de fibonacci.");
    }else{
        while(input > actual){
            baseCase1 += baseCase2;
            baseCase2 += actual;
            actual = baseCase1 + baseCase2;
        }
    
        if((input == actual) || (input == baseCase1) || (input == baseCase2)){
            printf("Esse número faz parte da sequência de fibonacci.");
        }else{
            printf("Esse número não faz parte da sequência de fibonacci.");
        }
    }
    
    return 0;
}

- Questão 03
Item a: 
Próximo elemento: 9
Lógica: a cada elemento se soma 2 unidades;

Item b: 
Próximo elemento: 128
Lógica: é a sequência da exponenciação da base 2^x a cada próximo elemento x é incrementado em mais uma unidade;

Item c: 
Próximo elemento: 49
Lógica: é a sequência de números que são quadrados perfeitos, números que multiplicados por eles mesmo resultam em quadrado perfeito, exemplo: 7 * 7 = 49;

Item d: 
Próximo elemento: 100
Lógica: a cada elemento se soma +8 unidades a partir do segundo elemento que foi acrescentado 12 unidades, acrescenta-se + 8 unidades sob o valor inicial para irmos do segundo para o terceiro elemento, ficando 12+8 = 20 -> 20 + 16 = 36 e repete o processo para os próximos números;

Item e: 
Próximo elemento: 13
Lógica: é a sequência de fibonacci que tem com caso base os dois primeiros números 1 e 1 e a partir do terceiro termo o próximo elemento se dá pela soma dos seus dois números anteriores a ele;


Item f: 
Próximo elemento: 200
Lógica: todos os elementos desse conjunto iniciam com a letra 'D', sendo assim, após o número 19 o próximo número que começa com a letra 'D' é o número 200.


- Questão 05
#include <stdio.h>
int main(){
    char phrase[] = "Hoje vai chover";
    // como eu já sei o tamanho da minha string que é igual a 16 considerando o '\0'
    // decidi dividir o tamanho da minha string e assim efetuar as
    // trocas dos caracteres pois agiliza o processo
    // sendo assim o '\0' troca com o H, o 'r' troca com o troca com o a letra 'o' e assim sucessivamente. até atingir a metade que é 8;
    // e por fim ele printa os caracteres trocados na posição invertida.
    for(int i = 0; i < 8; i++){
        char aux = phrase[i];
        phrase[i] = phrase[16 - i - 1];
        phrase[16 - i - 1] = aux;
    }

    for(int i = 0; i < 16; i++){
        printf("%c", phrase[i]);
    }

    return 0;
}