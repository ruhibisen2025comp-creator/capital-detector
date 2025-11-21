#include <stdio.h>
#include <string.h>

struct State {
    char name[40];
    char capital[40];
};

int main(void) {
    struct State s[] = {
        {"Andhra Pradesh", "Amaravati"},
        {"Arunachal Pradesh", "Itanagar"},
        {"Assam", "Dispur"},
        {"Bihar", "Patna"},
        {"Chhattisgarh", "Raipur"},
        {"Goa", "Panaji"},
        {"Gujarat", "Gandhinagar"},
        {"Haryana", "Chandigarh"},
        {"Himachal Pradesh", "Shimla"},
        {"Jharkhand", "Ranchi"},
        {"Karnataka", "Bengaluru"},
        {"Kerala", "Thiruvananthapuram"},
        {"Madhya Pradesh", "Bhopal"},
        {"Maharashtra", "Mumbai"},
        {"Manipur", "Imphal"},
        {"Meghalaya", "Shillong"},
        {"Mizoram", "Aizawl"},
        {"Nagaland", "Kohima"},
        {"Odisha", "Bhubaneswar"},
        {"Punjab", "Chandigarh"},
        {"Rajasthan", "Jaipur"},
        {"Sikkim", "Gangtok"},
        {"Tamil Nadu", "Chennai"},
        {"Telangana", "Hyderabad"},
        {"Tripura", "Agartala"},
        {"Uttar Pradesh", "Lucknow"},
        {"Uttarakhand", "Dehradun"},
        {"West Bengal", "Kolkata"}
    };

    int total = sizeof s / sizeof s[0];
    char input[40];
    int found = 0;

    printf("Enter state name: ");
    if (fgets(input, sizeof input, stdin) == NULL) {
        printf("Input error.\n");
        return 1;
    }
    for (int i = 0; input[i] != '\0'; i++) {
        if (input[i] == '\n') { input[i] = '\0'; break; }
    }

    for (int i = 0; i < total; i++) {
        if (strcmp(input, s[i].name) == 0) {
            printf("Capital of %s is %s\n", s[i].name, s[i].capital);
            found = 1;
            break;
        }
    }

    if (!found) puts("Please enter a valid state name.");
    return 0;
}
