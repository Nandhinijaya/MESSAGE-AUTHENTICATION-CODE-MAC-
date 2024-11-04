# Exp-13 MESSAGE-AUTHENTICATION-CODE-MAC-

# Aim:
To implement Message Authentication Code (MAC) for verifying
message integrity.

# Algorithm Steps:

1. Generate a shared secret key.
2. Create a message and compute the MAC using the key.
3. Send the message and the MAC to the recipient.
4. The recipient verifies the MAC using the shared key.
5. If the MAC matches, the message is authenticated.

# Program:
```
#include <stdio.h>
#include <string.h>

void compute_mac(char *message, char *key, char *mac) {
    for (int i = 0; i < strlen(message); i++) {
        mac[i] = message[i] ^ key[i % strlen(key)];
    }
    mac[strlen(message)] = '\0';  // Null-terminate the MAC string
}

int main() {
    printf("Experiment 13 - Message Authentication Code\n");
    printf("Developed by: Nandhini 212222100030\n");

    char message[] = "nandhini";
    char key[] = "secret";
    char mac[100];

    compute_mac(message, key, mac);

    printf("Message: %s\n", message);
    printf("Key: %s\n", key);

    printf("MAC (in hex): ");
    for (int i = 0; i < strlen(message); i++) {
        printf("%02X", (unsigned char)mac[i]);
    }
    printf("\n");

    return 0;
}

```
# Output:
![image](https://github.com/user-attachments/assets/d08ccc8e-6f99-4f8c-a49a-ff19dc652609)

# Result:
The MAC for the given message is successfully computed using a
secret key.
