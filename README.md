# 38.Bushra-Hussain-Maqpoon-Project-1
#include<iostream>
using namespace std;
char table[3][3]={{'1','2','3'},{'4','5','6'},{'7','8','9'}};
char turn='X';
int row,column;
void display_table()
{
		cout<<"Tic Tac Toe Game"<<endl;
	cout<<" Player1 [X] \n Player2 [O]\n\n";
	
	cout<<"\t     |     |     \n";
	cout<<"\t  "<<table[0][0]<<"  |  "<<table[0][1]<<"  |  "<<table[0][2]<<"  \n";
	cout<<"\t_____|_____|_____\n";
	cout<<"\t     |     |     \n";
	cout<<"\t  "<<table[1][0]<<"  |  "<<table[1][1]<<"  |  "<<table[1][2]<<"  \n";
	cout<<"\t_____|_____|_____\n";
	cout<<"\t     |     |     \n";
	cout<<"\t  "<<table[2][0]<<"  |  "<<table[2][1]<<"  |  "<<table[2][2]<<"  \n";
	cout<<"\t     |     |     \n";
}
void player_turn()
{
	int choice;
	if(turn=='X')
	{
	cout<<"\nPlayer1[X] turn:";
		
	}
		if(turn=='O')
	{
	cout<<"\nPlayer2[0] turn:";
		
	}
	cin>>choice;
	switch(choice)
	{
		case 1:
		row=0;column=0;break;
		case 2:
		row=0;column=1;break;
		case 3:
		row=0;column=2;break;	
	    case 4:
		row=1;column=0;break;
		case 5:
		row=1;column=1;break;
		case 6:
		row=1;column=2;break;
		case 7:
		row=2;column=0;break;
		case 8:
		row=2;column=1;break;
		case 9:
		row=2;column=2;break;
		default:
		  cout<<"Invalid choice\n:";
		  break;
	if(turn=='X')	  
	{
		table[row][column]='X';
		turn='0';
	}
	else
	{
		table[row][column]='O';
		turn='X';
	}
	}
}
int main()
{
    display_table();
    player_turn();
	display_table();
			
}
