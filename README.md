# Tictac
#include<stdio.h>
int  check(char , char);
char a[9]={'1','2','3','4','5','6','7','8','9'};
void gameName()
{
	printf("\n\t\t\tTic Tac Toe Game : \n");
}
int show()
{
	printf("\n\n\t\t\t---|---|---\n");
	printf("\t\t\t %c | %c | %c \n",a[0],a[1],a[2]);
	printf("\t\t\t---|---|---\n");
	printf("\t\t\t %c | %c | %c \n",a[3],a[4],a[5]);
	printf("\t\t\t---|---|---\n");
	printf("\t\t\t %c | %c | %c \n",a[6],a[7],a[8]);
}
void inputSymbol()
{
	printf("\n\tplayer1 symbol:x:\n");
	printf("\n\tplayer2 symbol:0:\n");

}
void start()
{
	char pa;
	printf("\nenter who will start the game: player 1 or player 2\n ");
	scanf("%c",&pa);
}
 void play()
 {
 	char p,s;
 	printf("\n enter position and symbol fot the  player :\n");
 	fflush(stdin);
 	scanf("%c",&p);
 	fflush(stdin);
 	scanf("%c",&s);
 	check(p,s);
 }
 int check(char p, char s)
 {
 int i;
 for(i=0;i<=8;i++)
 {
 	if(a[i]==p)
 	{
 		a[i]=s;
	 }
    }	
 }
 int end()
 {
 	if((a[0]=='x'&&a[1]=='x'&&a[2]=='x')||(a[0]=='x'&&a[3]=='x'&&a[6]=='x')||(a[0]=='x'&&a[4]=='x'&&a[8]=='x'))
 	return(100);
 	if((a[0]=='0'&&a[1]=='0'&&a[2]=='0')||(a[0]=='0'&&a[3]=='0'&&a[6]=='0')||(a[0]=='0'&&a[4]=='0'&&a[8]=='0'))
 	return(200);
 	else if(a[1]=='x'&&a[4]=='x'&&a[7]=='x')
 	return(100);
 	else if(a[1]=='0'&&a[4]=='0'&&a[7]=='0')
 	return(200);
 	else if(a[2]=='x'&&a[5]=='x'&&a[8]=='x')
 	return(100);
 	else if(a[2]=='0'&&a[5]=='0'&&a[8]=='0')
 	return(200);
 	else if(a[6]=='x'&&a[7]=='x'&&a[8]=='x')
 	return(100);
 	else if(a[6]=='0'&&a[7]=='0'&&a[8]=='0')
 	return(200);
 	return (300);
 }
int main()
{
	int k;
	gameName();
	show();
	inputSymbol();
	start();
	play();
	label:
	show();
	play();
	k=end();
	show();
	if(k==100)
		printf("\n player 1 won");
		else if(k==200)
			printf("\n player 2 won");
		else
			goto label;
	return 0;
}
