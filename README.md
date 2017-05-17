/*
   caesar.c encrypts the user's plaintext via a character shift when appropriate.
   CS50 pset2/caesar/c
*/

#include <stdio.h>
#include <cs50.h>
#include <ctype.h>
#include <string.h>

int main(int argc, string argv[])
{
    // Usage
    if (argc != 2)
    {
        printf("Usage: ./caesar <key>\n");
        return 1;
    }
    
    int k = atoi(argv[1]);
    
    printf("plaintext: ");
    string p = get_string();
    
    printf("ciphertext: ");
    
    for (int i = 0, n = strlen(p); i < n; i++)
    {
        if (isupper(p[i]))
        {
            printf("%c", (p[i] + k) % 26);
        }
        
        if (islower(p[i]))
        {
            printf("%c", (p[i] + k) % 26);
        }
        
        if (isdigit(p[i]))
        {
            printf("%c", p[i]);
        }
        
        if (ispunct(p[i]))
        {
            printf("%c", p[i]);
        }
        
        // if (p[i] == 32)
        // {
        //     printf("%c", p[i]);
        // }
    }
    
    printf("\n");
    
    return 0;
}
  
