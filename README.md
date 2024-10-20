#include<iostream>
using namespace std;
char a[7][6], turn;
int digit;
string moves;
char won;
int
main ()
{
  char opponent = 'o', player = 'x', turn;
  int number, i, j, choose, target;
  for (i = 0; i < 4; i++)
	{
	  for (j = 0; j < 6; j++)
		{
		  if (i == 2)
			{
			  if (j == 1 || j == 3)
				{
				  a[i][j] = '|';
				  continue;
				}
			  a[i][j] = ' ';
			}
		  if (i == 0 || i == 1)
			{
			  if (j == 1 || j == 3)
				{
				  a[i][j] = '|';
				  continue;
				}
			  a[i][j] = '_';
			}
		}
	}
  for (i = 0; i < 4; i++)
	{
	  for (j = 0; j < 5; j++)
		{
		  cout << a[i][j];
		}
	  cout << endl;
	}
  int count1 = 0, count2 = 0;
  while (count1 != 3 || count2 != 3)
	{

	  if (count1 < 3)
		{
		  cout << "Choose your cell from (0-8) : ";
		  cin >> choose;
		  turn = 'x';
		  target = choose;
		  if (target == 0)
			{
			  if ((a[0][0] == ' ') || (a[0][0] == '_'))
				{
				  a[0][0] = turn;
				  count1++;
				}
			}
		  else if (target == 1)
			{
			  if ((a[0][2] == ' ') || (a[0][2] == '_'))
				{
				  a[0][2] = turn;
				  count1++;
				}
			}
		  else if (target == 2)
			{
			  if ((a[0][4] == ' ') || (a[0][4] == '_'))
				{
				  a[0][4] = turn;
				  count1++;
				}
			}
		  else if (target == 3)
			{
			  if ((a[1][0] == ' ') || (a[1][0] == '_'))
				{
				  a[1][0] = turn;
				  count1++;
				}
			}
		  else if (target == 4)
			{
			  if ((a[1][2] == ' ') || (a[1][2] == '_'))
				{
				  a[1][2] = turn;
				  count1++;
				}
			}
		  else if (target == 5)
			{
			  if ((a[1][4] == ' ') || (a[1][4] == '_'))
				{
				  a[1][4] = turn;
				  count1++;
				}
			}
		  else if (target == 6)
			{
			  if ((a[2][0] == ' ') || (a[2][0] == '_'))
				{
				  a[2][0] = turn;
				  count1++;
				}
			}
		  else if (target == 7)
			{
			  if ((a[2][2] == ' ') || (a[2][2] == '_'))
				{
				  a[2][2] = turn;
				  count1++;
				}
			}
		  else if (target == 8)
			{
			  if ((a[2][4] == ' ') || (a[2][4] == '_'))
				{
				  a[2][4] = turn;
				  count1++;
				}
			}
		  else
			{
			  cout << "Inavalid move" << endl;
			  continue;
			}
		}
	  number = (rand () % 9);
	  target = number;
	  turn = 'o';
	  if (target == 0)
		{
		  if ((a[0][0] == ' ') || (a[0][0] == '_'))
			{
			  a[0][0] = turn;
			  count2++;
			}
		}
	  else if (target == 1)
		{
		  if ((a[0][2] == ' ') || (a[0][2] == '_'))
			{
			  a[0][2] = turn;
			  count2++;
			}
		}
	  else if (target == 2)
		{
		  if ((a[0][4] == ' ') || (a[0][4] == '_'))
			{
			  a[0][4] = turn;
			  count2++;
			}
		}
	  else if (target == 3)
		{
		  if ((a[1][0] == ' ') || (a[1][0] == '_'))
			{
			  a[1][0] = turn;
			  count2++;
			}
		}
	  else if (target == 4)
		{
		  if ((a[1][2] == ' ') || (a[1][2] == '_'))
			{
			  a[1][2] = turn;
			  count2++;
			}
		}
	  else if (target == 5)
		{
		  if ((a[1][4] == ' ') || (a[1][4] == '_'))
			{
			  a[1][4] = turn;
			  count2++;
			}
		}
	  else if (target == 6)
		{
		  if ((a[2][0] == ' ') || (a[2][0] == '_'))
			{
			  a[2][0] = turn;
			  count2++;
			}
		}
	  else if (target == 7)
		{
		  if ((a[2][2] == ' ') || (a[2][2] == '_'))
			{
			  a[2][2] = turn;
			  count2++;
			}
		}
	  else if (target == 8)
		{
		  if ((a[2][4] == ' ') || (a[2][4] == '_'))
			{
			  count2++;
			  a[2][4] = turn;
			}
		}
	  for (i = 0; i < 4; i++)
		{
		  for (j = 0; j < 5; j++)
			{
			  cout << a[i][j];
			}
		  cout << endl;
		}

	}
  int direction;
  turn = 'x';
  do
	{
	  if ((a[0][0] == a[0][2]) && (a[0][2] == a[0][4]))
		{
		  won = a[0][0];
		  if ((a[0][0] != ' ') && (a[0][0] != '_'))
			break;
		}
	  else if ((a[1][0] == a[1][2]) && (a[1][2] == a[1][4]))
		{
		  won = a[1][0];
		  if ((a[1][0] != ' ') && (a[1][0] != '_'))
			break;
		}
	  else if ((a[2][0] == a[2][2]) && (a[2][2] == a[2][4]))
		{
		  won = a[2][0];
		  if ((a[2][0] != ' ') && (a[2][0] != '_'))
			break;
		}
	  else if ((a[0][0] == a[1][0]) && (a[1][0] == a[2][0]))
		{
		  won = a[0][0];
		  if ((a[0][0] != ' ') && (a[0][0] != '_'))
			break;
		}
	  else if ((a[0][2] == a[1][2]) && (a[1][2] == a[2][2]))
		{
		  won = a[0][2];
		  if ((a[0][2] != ' ') && (a[0][2] != '_'))
			break;
		}
	  else if ((a[0][4] == a[1][4]) && (a[1][4] == a[2][4]))
		{
		  won = a[0][4];
		  if ((a[0][4] != ' ') && (a[0][4] != '_'))
			break;

		}
	  else if ((a[0][0] == a[1][2]) && (a[1][2] == a[2][4]))
		{
		  won = a[0][0];
		  if ((a[0][0] != ' ') && (a[0][0] != '_'))
			break;
		}
	  else if ((a[0][4] == a[1][2]) && (a[1][2] == a[2][0]))
		{
		  won = a[2][0];
		  if ((a[2][0] != ' ') && (a[2][0] != '_'))
			break;
		}
	  if (turn != 'o')
		turn = 'x';
	  if (turn == 'x')
		{
		  cout << "select the cell to move (0-8) : ";
		  cin >> digit;
		  cout << "enter left, right, up or down : ";
		  cin >> moves;
		  if (digit == 0)
			{
			  if ((a[0][0] == ' ') || (a[0][0] == '_'))
				{

				  cout << "cell is empty" << endl;
				  continue;
				}
			  if (moves == "right")
				{
				  a[0][2] = turn;
				  a[0][0] = '_';
				}
			  else if (moves == "down")
				{
				  a[1][0] = turn;
				  a[0][0] = '_';
				}
			  else
				{
				  cout << "Invalid move! " << endl;
				  continue;
				}
			}
		  else if (digit == 1)
			{
			  if ((a[0][2] == ' ') || (a[0][2] == '_'))
				{
				  cout << "cell is empty" << endl;
				  continue;
				}
			  if (moves == "left")
				{
				  a[0][0] = turn;
				  a[0][2] = '_';
				}
			  else if (moves == "right")
				{

				  a[0][4] = turn;
				  a[0][2] = '_';
				}
			  else if (moves == "down")
				{

				  a[1][2] = turn;
				  a[0][2] = '_';
				}
			  else
				{
				  cout << "Invalid move!" << endl;
				  continue;
				}
			}
		  else if (digit == 2)
			{
			  if (a[0][4] == ' ' || a[0][4] == '_')
				{
				  cout << "cell is empty" << endl;
				  continue;
				}
			  if (moves == "left")
				{
				  a[0][2] = turn;
				  a[0][4] = '_';
				}
			  else if (moves == "down")
				{

				  a[1][4] = turn;
				  a[0][4] = '_';
				}
			}
		  else if (digit == 3)
			{

			  if (a[1][0] == ' ' || a[1][0] == '_')
				{
				  cout << "cell is empty" << endl;
				  continue;
				}
			  if (moves == "right")
				{
				  a[1][2] = turn;
				  a[1][0] = '_';
				}
			  else if (moves == "down")
				{
				  a[2][0] = turn;
				  a[1][0] = '_';
				}
			  else if (moves == "up")
				{

				  a[0][0] = turn;
				  a[1][0] = '_';
				}
			  else
				{
				  cout << "Invalid move!" << endl;
				  continue;
				}
			}
		  else if (digit == 4)
			{
			  if ((a[1][2] == '_') || (a[1][2] == ' '))
				{
				  cout << "cell is empty" << endl;
				  continue;
				}
			  if (moves == "left")
				{
				  a[1][0] = turn;
				  a[1][2] = '_';
				}
			  else if (moves == "right")
				{
				  a[1][4] = turn;
				  a[1][2] = '_';
				}
			  else if (moves == "up")
				{
				  a[0][2] = turn;
				  a[1][2] = '_';
				}
			  else if (moves == "down")
				{
				  a[2][2] = turn;
				  a[1][2] = '_';
				}
			  else
				{
				  cout << "Invalid move!";
				  continue;
				}
			}
		  else if (digit == 5)
			{
			  if ((a[1][4] == ' ') || (a[1][4] == '_'))
				{
				  cout << "cell is empty" << endl;
				  continue;
				}
			  if (moves == "left")
				{
				  a[1][2] = turn;
				  a[1][4] = '_';
				}
			  else if (moves == "up")
				{
				  a[0][4] = turn;
				  a[1][4] = '_';
				}
			  else if (moves == "down")
				{
				  a[2][4] = turn;
				  a[1][4] = '_';
				}
			  else
				{
				  cout << "Invalid move!" << endl;
				  continue;
				}
			}
		  else if (digit == 6)
			{
			  if ((a[2][0] == ' ') || (a[2][0] == '_'))
				{
				  cout << "cell is empty" << endl;
				  continue;
				}
			  if (moves == "right")
				{
				  a[2][2] = turn;
				  a[2][0] = ' ';
				}
			  else if (moves == "up")
				{
				  a[1][0] = turn;
				  a[2][0] = ' ';
				}
			  else
				{
				  cout << "Invalid move!" << endl;
				  continue;
				}
			}
		  else if (digit == 7)
			{
			  if ((a[2][2] == ' ') || (a[2][2] == '_'))
				{
				  cout << "cell is empty" << endl;
				  continue;
				}
			  if (moves == "left")
				{
				  a[2][0] = turn;
				  a[2][2] = ' ';
				}
			  else if (moves == "right")
				{
				  a[2][4] = turn;
				  a[2][2] = ' ';
				}
			  else if (moves == "up")
				{

				  a[1][2] = turn;
				  a[2][2] = ' ';
				}
			  else
				{
				  cout << "Invalid move!" << endl;
				  continue;
				}
			}
		  else if (digit == 8)
			{
			  if ((a[2][4] == ' ') || (a[2][4] == '_'))
				{
				  cout << "cell is empty" << endl;
				  continue;
				}
			  if (moves == "left")
				{
				  a[2][2] = turn;
				  a[2][4] = ' ';
				}
			  else if (moves == "up")
				{
				  a[1][4] = turn;
				  a[2][4] = ' ';
				}
			  else
				{
				  cout << "Invalid move!" << endl;
				  continue;
				}
			}
		  else
			{
			  cout << "Invalid cell" << endl;
			  continue;
			}
		}
	  for (i = 0; i < 4; i++)
		{
		  for (j = 0; j < 5; j++)
			{
			  cout << a[i][j];
			}
		  cout << endl;
		}
		 if ((a[0][0] == a[0][2]) && (a[0][2] == a[0][4]))
		{
		  won = a[0][0];
		  if ((a[0][0] != ' ') && (a[0][0] != '_'))
			break;
		}
	  else if ((a[1][0] == a[1][2]) && (a[1][2] == a[1][4]))
		{
		  won = a[1][0];
		  if ((a[1][0] != ' ') && (a[1][0] != '_'))
			break;
		}
	  else if ((a[2][0] == a[2][2]) && (a[2][2] == a[2][4]))
		{
		  won = a[2][0];
		  if ((a[2][0] != ' ') && (a[2][0] != '_'))
			break;
		}
	  else if ((a[0][0] == a[1][0]) && (a[1][0] == a[2][0]))
		{
		  won = a[0][0];
		  if ((a[0][0] != ' ') && (a[0][0] != '_'))
			break;
		}
	  else if ((a[0][2] == a[1][2]) && (a[1][2] == a[2][2]))
		{
		  won = a[0][2];
		  if ((a[0][2] != ' ') && (a[0][2] != '_'))
			break;
		}
	  else if ((a[0][4] == a[1][4]) && (a[1][4] == a[2][4]))
		{
		  won = a[0][4];
		  if ((a[0][4] != ' ') && (a[0][4] != '_'))
			break;

		}
	  else if ((a[0][0] == a[1][2]) && (a[1][2] == a[2][4]))
		{
		  won = a[0][0];
		  if ((a[0][0] != ' ') && (a[0][0] != '_'))
			break;
		}
	  else if ((a[0][4] == a[1][2]) && (a[1][2] == a[2][0]))
		{
		  won = a[2][0];
		  if ((a[2][0] != ' ') && (a[2][0] != '_'))
			break;
		}
	  turn = 'o';
	  digit = (rand () % 9);
	  direction = rand () % 4 + 1;
	  if (direction == 1)
		{
		  moves = "left";
		}
	  else if (direction == 2)
		{
		  moves = "right";
		}
	  else if (direction == 3)
		{
		  moves = "up";
		}
	  else if (direction == 4)
		{
		  moves = "down";
		}
	  if (digit == 0)
		{
		  if ((a[0][0] == ' ') || (a[0][0] == '_') || (a[0][0] == 'x'))
			{
			  continue;
			}
		  if (moves == "right")
			{
			  if ((a[0][2] != 'x') && (a[0][2] != 'o'))
				a[0][2] = turn;
			  else
				continue;
			  a[0][0] = '_';
			}
		  else if (moves == "down")
			{
			  if ((a[1][0] != 'x') && (a[1][0] != 'o'))
				a[1][0] = turn;
			  else
				continue;
			  a[0][0] = '_';
			}
		  else
			{
			  continue;
			}
		}

	  else if (digit == 1)
		{
		  if ((a[0][2] == ' ') || (a[0][2] == '_') || (a[0][2] == 'x'))
			{
			  continue;
			}
		  if (moves == "left")
			{
			  if ((a[0][4] != 'x') && (a[1][2] != 'o'))
				a[0][4] = turn;
			  else
				continue;
			  a[0][2] = '_';
			}
		  else if (moves == "right")
			{
			  if ((a[0][2] != 'x') && (a[0][2] != 'o'))
				a[0][0] = turn;
			  else
				continue;
			  a[0][2] = '_';
			}
		  else if (moves == "down")
			{
			  if ((a[1][2] != 'x') && (a[1][2] != 'o'))
				a[1][2] = turn;
			  else
				continue;
			  a[0][2] = '_';
			}
		  else
			{
			  continue;
			}
		}
	  else if (digit == 2)
		{
		  if ((a[0][4] == ' ') || (a[0][4] == '_') || (a[0][4] == 'x'))
			{
			  continue;
			}
		  if (moves == "left")
			{
			  if ((a[0][2] != 'x') && (a[0][2] != 'o'))
				a[0][2] = turn;
			  else
				continue;
			  a[0][4] = '_';
			}
		  else if (moves == "down")
			{
			  if ((a[1][4] != 'x') && (a[1][4] != 'o'))
				a[1][4] = turn;
			  else
				continue;
			  a[0][4] = '_';
			}
		}
	  else if (digit == 3)
		{

		  if ((a[1][0] == ' ') || (a[1][0] == '_') || (a[1][0] == 'x'))
			{
			  continue;
			}
		  if (moves == "right")
			{
			  if ((a[1][2] != 'x') && (a[1][2] != 'o'))
				a[1][2] = turn;
			  else
				continue;
			  a[1][0] = '_';
			}
		  else if (moves == "down")
			{
			  if ((a[2][0] != 'x') && (a[2][0] != 'o'))
				a[2][0] = turn;
			  else
				continue;
			  a[1][0] = '_';
			}
		  else if (moves == "up")
			{
			  if ((a[0][0] != 'x') && (a[0][0] != 'o'))
				a[0][0] = turn;
			  else
				continue;
			  a[1][0] = '_';
			}
		  else
			{
			  continue;
			}
		}
	  else if (digit == 4)
		{
		  if (a[1][2] == ' ' || a[1][2] == '_' || (a[1][2] == 'x'))
			{
			  continue;
			}
		  if (moves == "left")
			{
			  if ((a[1][4] != 'x') && (a[1][4] != 'o'))
				a[1][4] = turn;
			  else
				continue;
			  a[1][2] = '_';
			}
		  else if (moves == "right")
			{
			  if ((a[1][0] != 'x') && (a[1][0] != 'o'))
				a[1][0] = turn;
			  else
				continue;
			  a[1][2] = '_';
			}
		  else if (moves == "up")
			{
			  if ((a[0][2] != 'x') && (a[0][2] != 'o'))
				a[0][2] = turn;
			  else
				continue;
			  a[1][2] = '_';
			}
		  else if (moves == "down")
			{
			  if ((a[2][2] != 'x') && (a[2][2] != 'o'))
				a[2][2] = turn;
			  else
				continue;
			  a[1][2] = '_';
			}
		  else
			{
			  continue;
			}
		}
	  else if (digit == 5)
		{
		  if ((a[1][4] == ' ') || (a[1][4] == '_') || (a[1][4] == 'x'))
			{
			  continue;
			}
		  if (moves == "left")
			{
			  if ((a[1][2] != 'x') && (a[1][2] != 'o'))
				a[1][2] = turn;
			  else
				continue;
			  a[1][4] = '_';
			}
		  else if (moves == "up")
			{
			  if ((a[0][4] != 'x') && (a[0][4] != 'o'))
				a[0][4] = turn;
			  else
				continue;
			  a[1][4] = '_';
			}
		  else if (moves == "down")
			{
			  if ((a[2][4] != 'x') && (a[2][4] != 'o'))
				a[2][4] = turn;
			  else
				continue;
			  a[1][4] = '_';
			}
		  else
			{
			  continue;
			}
		}
	  else if (digit == 6)
		{
		  if ((a[2][0] == ' ') || (a[2][0] == '_') || (a[2][0] == 'x'))
			{
			  continue;
			}
		  if (moves == "right")
			{
			  if ((a[2][2] != 'x') && (a[2][2] != 'o'))
				a[2][2] = turn;
			  else
				continue;
			  a[2][0] = ' ';
			}
		  else if (moves == "up")
			{
			  if ((a[1][0] != 'x') && (a[1][0] != 'o'))
				a[1][0] = turn;
			  else
				continue;
			  a[2][0] = ' ';
			}
		  else
			{
			  continue;
			}
		}
	  else if (digit == 7)
		{
		  if ((a[2][2] == ' ') || (a[2][2] == '_') || (a[2][2] == 'x'))
			{
			  continue;
			}
		  if (moves == "left")
			{
			  if ((a[2][0] != 'x') && (a[2][0] != 'o'))
				a[2][0] = turn;
			  else
				continue;
			  a[2][2] = ' ';
			}
		  else if (moves == "right")
			{
			  if ((a[2][4] != 'x') && (a[2][4] != 'o'))
				a[2][4] = turn;
			  else
				continue;
			  a[2][2] = ' ';
			}
		  else if (moves == "up")
			{
			  if ((a[1][2] != 'x') && (a[1][2] != 'o'))
				a[1][2] = turn;
			  else
				continue;
			  a[2][2] = ' ';
			}
		  else
			{
			  continue;
			}
		}
	  else if (digit == 8)
		{
		  if ((a[2][4] == ' ') || (a[2][4] == '_') || (a[2][4] == 'x'))
			{
			  continue;
			}
		  if (moves == "left")
			{
			  if ((a[2][2] != 'x') && (a[2][2] != 'o'))
				a[2][2] = turn;
			  else
				continue;
			  a[2][2] = '_';
			}
		  else if (moves == "up")
			{
			  if ((a[1][4] != 'x') && (a[1][4] != 'o'))
				a[1][4] = turn;
			  else
				continue;
			  a[2][4] = ' ';
			}
		  else
			{
			  continue;
			}
		}
	  else
		{
		  continue;
		}
	  turn = 'p';
	  if ((a[0][0] == a[0][2]) && (a[0][2] == a[0][4]))
		{
		  won = a[0][0];
		  if ((a[0][0] != ' ') && (a[0][0] != '_'))
			break;
		}
	  else if ((a[1][0] == a[1][2]) && (a[1][2] == a[1][4]))
		{
		  won = a[1][0];
		  if ((a[1][0] != ' ') && (a[1][0] != '_'))
			break;
		}
	  else if ((a[2][0] == a[2][2]) && (a[2][2] == a[2][4]))
		{
		  won = a[2][0];
		  if ((a[2][0] != ' ') && (a[2][0] != '_'))
			break;
		}
	  else if ((a[0][0] == a[1][0]) && (a[1][0] == a[2][0]))
		{
		  won = a[0][0];
		  if ((a[0][0] != ' ') && (a[0][0] != '_'))
			break;
		}
	  else if ((a[0][2] == a[1][2]) && (a[1][2] == a[2][2]))
		{
		  won = a[0][2];
		  if ((a[0][2] != ' ') && (a[0][2] != '_'))
			break;
		}
	  else if ((a[0][4] == a[1][4]) && (a[1][4] == a[2][4]))
		{
		  won = a[0][4];
		  if ((a[0][4] != ' ') && (a[0][4] != '_'))
			break;

		}
	  else if ((a[0][0] == a[1][2]) && (a[1][2] == a[2][4]))
		{
		  won = a[0][0];
		  if ((a[0][0] != ' ') && (a[0][0] != '_'))
			break;
		}
	  else if ((a[0][4] == a[1][2]) && (a[1][2] == a[2][0]))
		{
		  won = a[2][0];
		  if ((a[2][0] != ' ') && (a[2][0] != '_'))
			break;
		}
	  for (i = 0; i < 4; i++)
		{
		  for (j = 0; j < 5; j++)
			{
			  cout << a[i][j];
			}
		  cout << endl;
		}
		char opinion;
		cout<<"do you want to continue (y/n) : ";
		cin >> opinion;
		if(opinion=='n')
		break;
	}
  while (true);
  for (i = 0; i < 4; i++)
	{
	  for (j = 0; j < 5; j++)
		{
		  cout << a[i][j];
		}
	  cout << endl;
	}
  if (won == 'x')
	cout << "You won!!";
  else if (won == 'o')
	cout << "Opponent won!!";
  else
	cout << "It's a draw!";
  return 0;

}

