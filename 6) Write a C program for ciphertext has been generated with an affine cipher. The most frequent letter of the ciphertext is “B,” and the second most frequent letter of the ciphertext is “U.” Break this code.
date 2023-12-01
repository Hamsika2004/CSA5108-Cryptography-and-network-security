#include <stdio.h>
#include <string.h>
char decryptChar(int c, int a, int b) 
{
 return ((a * (c - b)) % 26 + 26) % 26 + 'A';
}
int main() 
{
 char ciphertext[1000];
 printf("Enter the ciphertext: ");
 scanf("%s", ciphertext);
 int mostFrequent = ciphertext[0];
 int secondMostFrequent = ciphertext[1];
 printf("Finding possible keys...\n");
 for (int a = 1; a < 26; a++) 
 {
 for (int b = 0; b < 26; b++) 
 {
 if (decryptChar(mostFrequent, a, b) == mostFrequent &&
 decryptChar(secondMostFrequent, a, b) == secondMostFrequent) 
 {
 printf("Possible key found: a = %d, b = %d\n", a, b);
 }
 }
 }
 return 0;
}
