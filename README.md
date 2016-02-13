# Caeser Cipher
Encrytps Data using Caeser Cipher
#include<stdio.h>
#include<cs50.h>
#include<stdlib.h>
#include<string.h>
 
 
int main(int argc,string argv[])
 {
  int key,i,a,b,c,d;
  string plain_txt;
  if(argc!=2)
  {
  printf(" please enter valid arguments \n");   //returns 1 and warns user if there are more or less than two command-line arguements
  return 1;
  }
  key=atoi(argv[1]); //to get the key
  plain_txt=GetString();  //gets the string to cipher
  for(i=0;i<strlen(plain_txt);i++)
      {
        if(plain_txt[i]>64 && plain_txt[i]<91)
           {                                           // to encipher upper case letters 
             b= (int)plain_txt[i];                    //   converts ith element of the palin_text to int
             a=b-64;                                 //       coverting jth element of key from ascii value to corresponding alphabetical rank
             c=(a+key)%26;                          //        enciphering formula
             d=c+64;
             plain_txt[i]=d;     
            }
       if(plain_txt[i]>96 && plain_txt[i]<124)
           {
             b= (int)plain_txt[i];
             a=b-97;     
             c=(a+key)%26;
             d=c+97;
             plain_txt[i]=d; 
           }               
      }
     printf("%s\n",plain_txt);                         
      } 
 
