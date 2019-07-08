#include<stdio.h>
#include<string.h>
#include<stdlib.h>
int main()
{
    int i,key;
    int num;
    scanf("%d\n",&num);

    char plain[100],cipher[100];
    gets(plain);
    scanf("\n%d",&key);
    key=key%26; // adjusting key
    fflush(stdin);

    for(i=0;i<strlen(plain);i++)
    {
        if(isalpha(plain[i]))
        {
            if(islower(plain[i]))
                cipher[i]=(plain[i]+key-'a')%26+'a';
            else
                cipher[i]=(plain[i]+key-'A')%26+'A';
        }
        else
            cipher[i]=plain[i];
    }
    cipher[i]='\0';
    printf("%s",cipher);
    
    return 0;
}
