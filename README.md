# EXP-11-Elliptic-curve-cryptography

## AIM:
To write a program to implement Elliptic curve cryptography (ECC).

## ALGORITHM:

### STEP-1: 
Input Parameters
### STEP-2: 
Calculate Public Keys
### STEP-3: 
Display Public Keys
### STEP-4: 
Calculate Shared Secret Keys
### STEP-5: 
Display Shared Secret Keys
### STEP-6: 
Check If Shared Secrets Match
### STEP-7: 
Input the Message to Encrypt
### STEP-8: 
Encrypt the Message
### STEP-9: 
Display the Encrypted Message and the Decrypted Message.

## PROGRAM:
```c
#include <stdio.h>
int mod_add(int a, int b, int mod) {
return (a + b) % mod;
}

int mod_mult(int a, int b, int mod) {
return (a * b) % mod;
}

int point_mulƟplicaƟon(int G, int private_key, int mod) {
return mod_mult(G, private_key, mod); // G * private_key % mod
}
int main() {
int G, nA, nB, p;  
int PA, PB;
int KA, KB; 
int message, encrypted_message, decrypted_message;
printf("\n ********EllipƟc Curve Cryptography(ECC)********\n\n");
printf("\n NAME:SANJAY S REG NO:212223040184\n\n");
printf("Enter the base point (G): ");
scanf("%d", &G);
printf("Enter the prime modulus (p): ");
scanf("%d", &p);


printf("Enter private key for Alice (nA): ");
scanf("%d", &nA);
printf("Enter private key for Bob (nB): ");
scanf("%d", &nB);
PA = point_mulƟplicaƟon(G, nA, p); 
PB = point_mulƟplicaƟon(G, nB, p);
printf("Alice's public key (PA) = %d\n", PA);
printf("Bob's public key (PB) = %d\n", PB);

KA = point_mulƟplicaƟon(PB, nA, p); 
KB = point_mulƟplicaƟon(PA, nB, p); 
printf("Shared secret calculated by Alice (KA) = %d\n", KA);
printf("Shared secret calculated by Bob (KB) = %d\n", KB);

if (KA == KB) {
printf("Success! Both parƟes have the same shared secret.\n");

printf("Enter the message to encrypt (as an integer): ");
scanf("%d", &message);

encrypted_message = mod_add(message, KA, p);
printf("Encrypted message: %d\n", encrypted_message);

decrypted_message = (encrypted_message - KA + p) % p;

printf("Decrypted message: %d\n", decrypted_message);
} else {
printf("Error! The shared secrets do not match.\n");
}
return 0;
}
```
## Output:

![image](https://github.com/user-attachments/assets/9faebc69-2823-4529-b054-302eed1eebbf)

## Result:
Thus the Elliptic curve cryptography (ECC) had been implemented successfully.
