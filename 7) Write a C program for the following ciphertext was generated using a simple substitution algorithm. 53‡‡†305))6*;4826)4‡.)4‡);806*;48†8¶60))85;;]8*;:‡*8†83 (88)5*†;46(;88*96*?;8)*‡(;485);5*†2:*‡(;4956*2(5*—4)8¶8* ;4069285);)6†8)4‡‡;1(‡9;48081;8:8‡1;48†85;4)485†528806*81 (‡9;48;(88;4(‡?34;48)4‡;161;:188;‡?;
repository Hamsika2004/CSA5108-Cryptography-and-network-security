#include <stdio.h>
#include <string.h>
#include <ctype.h>
void decryptCiphertext(char ciphertext[]) 
{
    int i, j;
    int len = strlen(ciphertext);
    char decrypted[len];
	strcpy(decrypted, ciphertext);
	char eGuess = 'e';
    char mostFrequent = '\0';
    int maxFrequency = 0;
    int frequency[256] = {0};  
	for (i = 0; i < len; i++) 
	{
        if (isalpha(decrypted[i])) 
		{
            decrypted[i] = tolower(decrypted[i]);
            frequency[decrypted[i]]++;
			if (frequency[decrypted[i]] > maxFrequency) 
			{
                maxFrequency = frequency[decrypted[i]];
                mostFrequent = decrypted[i];
            }
        }
    }
	for (i = 0; i < len; i++) 
	{
        if (decrypted[i] == mostFrequent) 
		{
            decrypted[i] = eGuess;
        }
    }
	char tGuess = 't';
    char hGuess = 'h';

    for (i = 0; i < len; i++) 
	{
        if (decrypted[i] == tGuess || decrypted[i] == hGuess) 
		{
            continue;
        }
		if (isalpha(decrypted[i])) 
		{
            if (decrypted[i] != mostFrequent && decrypted[i] != tGuess) 
			{
                decrypted[i] = tGuess;
            } 
			else 
			{
               for (j = i + 1; j < len; j++) 
				{
                    if (isalpha(decrypted[j]) && decrypted[j] != mostFrequent && decrypted[j] != tGuess && decrypted[j] != hGuess) 
					{
                        decrypted[j] = hGuess;
                        break;
                    }
                }
            }
        }
    }
    printf("Decrypted message:\n%s\n", decrypted);
}
int main()
{
    char ciphertext[] = "53‡‡†305))6*;4826)4‡.)4‡);806*;48†8¶60))85;;]8*;:‡8†83 (88)5†;46(;88*96*?;8)‡(;485);5†2:‡(;4956*2(5—4)8¶8* ;4069285);)6†8)4‡‡;1(‡9;48081;8:8‡1;48†85;4)485†528806*81 (‡9;48;(88;4(‡?34;48)4‡;161;:188;‡?;";
	decryptCiphertext(ciphertext);
return 0;
}
