#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main()
{
    int i;
    int runTime;
    int die1;
    int die2;
    int die3;
    int temp;
    int total;
    char guess;
    int count = 0;
    srand(time(NULL));

    printf("How many times do you want to play?\n");
    scanf(" %d", &runTime);
    printf("");

    die1 = ( (rand() % 6) + 1);
    die2 = ( (rand() % 6) + 1);
    die3 = ( (rand() % 6) + 1);
    total = (die1 + die2 + die3);

    if(runTime != 0){

        printf("Die 1: %d\n", die1);
        printf("Die 2: %d\n", die2);
        printf("Die 3: %d\n", die3);
        printf("-------------------\n");
        printf("Total: %d\n\n", total);
        temp = total;

        printf("Do you think the next total will be higher, the same, or lower than the previous total? (h, s, l) \n\n");
        scanf(" %c", &guess);

        for(i = 0; i < runTime - 1; i++){
            die1 = ( (rand() % 6) + 1);
            die2 = ( (rand() % 6) + 1);
            die3 = ( (rand() % 6) + 1);
            total = (die1 + die2 + die3);

            printf("Die 1: %d\n", die1);
            printf("Die 2: %d\n", die2);
            printf("Die 3: %d\n", die3);
            printf("-------------------");
            printf("Total: %d\n", total);

            if( (total > temp) && (guess == 'h') ){
                printf("You guessed correctly!\n");
                count++;
            }else if( (total == temp) && (guess == 's') ){
                printf("You guessed correctly!\n");
                count++;
            }else if( (total < temp) && (guess == 'l') ){
                printf("You guessed correctly!\n");
                count++;
            }else{
                printf("You guessed incorrectly :(\n");
            }
            temp = total;
            printf("Do you think the next total will be higher, the same, or lower than the previous total? (h, s, l) \n");
            scanf(" %c", &guess);

        }
    printf("You got a total of %d guesses correct!", count);
     }else{
    printf("Goodbye.");
    }
    return 0;
    
