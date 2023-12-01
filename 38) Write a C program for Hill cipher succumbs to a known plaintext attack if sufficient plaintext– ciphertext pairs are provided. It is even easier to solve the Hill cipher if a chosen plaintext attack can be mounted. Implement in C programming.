#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <ctype.h>
#include <math.h>
#define MAX_LEN 100
int charToNum(char c) {
 if (isupper(c)) {
 return c - 'A';
 } else if (islower(c)) {
 return c - 'a';
 }
 return -1; 
}
char numToChar(int num) {
 return num + 'A';
}
void encryptHill(char *text, int *keyMatrix, int keySize) {
 int i,j,k,textLen = strlen(text);
 int encrypted[MAX_LEN] = {0};
 for ( i = 0; i < textLen; i += keySize) {
 for ( j = 0; j < keySize; j++) {
 int sum = 0;
 for (k = 0; k < keySize; k++) {
 sum += keyMatrix[j * keySize + k] * charToNum(text[i + k]);
 }
 encrypted[i + j] = sum % 26;
 }
 }
 for (i = 0; i < textLen; i++) {
 text[i] = numToChar(encrypted[i]);
 }
}
int main() {
char plaintext[MAX_LEN];
 int keySize;
 printf("Enter the plaintext: ");
 gets(plaintext);
 printf("Enter the size of the key matrix: ");
 scanf("%d", &keySize);
 int i,j,keyMatrix[MAX_LEN * MAX_LEN];
 printf("Enter the key matrix (row by row):\n");
 for ( i = 0; i < keySize; i++) {
 for ( j = 0; j < keySize; j++) {
 scanf("%d", &keyMatrix[i * keySize + j]);
 }
 }
 int textLen = strlen(plaintext);
 int padding = keySize - (textLen % keySize);
 if (padding < keySize) {
 for ( i = 0; i < padding; i++) {
 plaintext[textLen + i] = 'X';
 }
 plaintext[textLen + padding] = '\0';
 }
 encryptHill(plaintext, keyMatrix, keySize);
 printf("Encrypted text: %s\n", plaintext);
 return 0;
}
