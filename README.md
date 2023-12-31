#include<iostream>
using namespace std;
char table[3][3]={{'1','2','3'},{'4','5','6'},{'7','8','9'}};
char turn='X';
int row,column;
bool draw=false;
void display_table()
{
	system("cls");
    cout<<"Tic Tac Toe Game";
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
    }  
	if(turn=='X' && table[row][column]!='X'&& table[row][column]!='O' )	  
	{
		table[row][column]='X';
		turn='O';
	}
	else if(turn=='O' && table[row][column]!='O'&& table[row][column]!='X' )
	{
		table[row][column]='O';
		turn='X';
	}
	else
	{
	cout<<"Box already filled!\nPlease try again\n";
	player_turn(); //Recusrive call to allow player to choose again 
    }
    display_table();
}
bool gameover()
{
	//check win
	for(int i=0;i<3;i++)
	{
	if(table[i][0]==table[i][1] && table[i][0]==table[i][2] || table[0][i]==table[1][i] && table[0][i]==table[2][i])
	return false;
	if((table[0][0]==table[1][1] && table[0][0]==table[2][2]) || (table[0][2]==table[1][1] && table[0][2]==table[2][0]))
	return false;
    }
	// check if there is any box not filled
	for(int i=0;i<3;i++)
	{
	for(int j=0;j<3;j++)
	if( table[i][j]!='X'&& table[i][j]!='O')
	return true;  
    }
    //game draws
    draw=true;
    return false;
}
int main()
{
	while(gameover())
	{	
      display_table();
      player_turn(); 
    }
    if (turn=='X'&& draw==false)
    {
    cout<<"PLayer2[O] Wins! Congratulations\n";
    }  
    else if (turn=='O' && draw==false)
	{
    cout<<"Player1[X] Wins! Congratularions\n";
    }
    else 
    cout<<"Game Draws\n";
    return 0;
}
