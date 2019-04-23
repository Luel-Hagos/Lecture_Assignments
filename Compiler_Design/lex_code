%option noyywrap
%{
	#include<stdio.h>
	int count=0;
	int sep=0;
	int opr=0;
%}
letter [a-zA-Z]
digitt [0-9]
id ([a-zA-Z_][0-9])+|[a-zA-Z_]*
notid ({digitt}{letter})+
%%
[\t\n]+("auto")|("double")|("int")|("struct")|("break")|("else")|("long")|("switch")|("case")|("enum")|("register")|("typedef")|("char")|("extern")|("return")|("union")|("continue")|("for")|("signed")|("void")|("do")|("if")|("static")|("while")|("default")|("goto")|("sizeof")|("volatile")|("const")|("float")|("short") {printf("%s is a keyword\n", yytext);}
{id} {printf("%s is an identifier\n", yytext); count++;}
[{}()!~#$_<>^&:]|[\\]|[\|]|[\[\]\"\?\.\,\'\]|[\;]  {ECHO;printf( " is a Separator\n",yytext); sep++;}
{notid} {printf("%s is not an identifier\n", yytext);}
[+-/=*%]|([-][-])|([+][+])   {ECHO;printf( " is an Operator\n",yytext); opr++;}
%%
 main()
{
FILE *fp;
char file[10];
printf("\nEnter the filename: ");
scanf("%s", file);
fp=fopen(file,"r");
yyin=fp;
yylex();
printf("************************************\n");
printf("Total identifiers are: %d\n", count);
printf("Total Operators are: %d\n", opr);
printf("Total Separators are: %d\n", sep);

}
