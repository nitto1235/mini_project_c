🏏 Cricket Score Display System
📘 Mini Project Report

Submitted By:
Name: Nitto Roy
UID: 25BCA10178
Course: BCA (Bachelor of Computer Application)
Date of Submission: 04-10-2025



#include <stdio.h>
#include <string.h>

struct Match {
    char team1[30];
    char team2[30];
    int totalOvers;
    int runs;
    int wickets;
    float overs;
};

int main() {
    struct Match m;
    int choice;
    m.runs = 0;
    m.wickets = 0;
    m.overs = 0.0;

    printf("===== CRICKET SCORE DISPLAY SYSTEM =====\n");
    printf("Enter Team 1 Name: ");
    gets(m.team1);
    printf("Enter Team 2 Name: ");
    gets(m.team2);
    printf("Enter Total Overs: ");
    scanf("%d", &m.totalOvers);

    do {
        printf("\n----- MENU -----\n");
        printf("1. Update Score\n");
        printf("2. Display Scoreboard\n");
        printf("3. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch(choice) {
            case 1: {
                int newRuns, newWickets;
                float newOvers;
                printf("\nEnter Runs Scored: ");
                scanf("%d", &newRuns);
                m.runs += newRuns;
                printf("Enter Wickets Fallen (add 0 if none): ");
                scanf("%d", &newWickets);
                m.wickets += newWickets;
                printf("Enter Overs Completed: ");
                scanf("%f", &newOvers);
                m.overs = newOvers;
                printf("Score Updated Successfully!\n");
                break;
            }

            case 2:
                printf("\n========== LIVE SCOREBOARD ==========\n");
                printf("Match: %s vs %s\n", m.team1, m.team2);
                printf("Score: %d/%d in %.1f overs\n", m.runs, m.wickets, m.overs);
                printf("Overs Remaining: %.1f\n", m.totalOvers - m.overs);
                printf("=====================================\n");
                break;

            case 3:
                printf("Exiting the program... Thank you!\n");
                break;

            default:
                printf("Invalid choice! Try again.\n");
        }
    } while(choice != 3);

    return 0;
}
