#include <windows.h>
#include <stdio.h>
#include <conio.h>
int main()
{
	char str[9][12] = {
		 "*#*********"
		,"***###*###*"
		,"###**#****#"
		,"*#**###**#*"
		,"***********"
		,"#####*##*##"
		,"**#*****#*E"
		,"***#*###**#"
		,"*#*********" };
	void gotoxy(int x, int y);
	int i, j;
	for (i = 0; i < 9; i++)
	{
		for (j = 0; j < 12; j++)
		{
			printf("%c", str[i][j]);
		}
		printf("\n");
	}
	int cax = 0, cay = 0;
	int move_x = 0, move_y = 0;
	gotoxy(0, 0);
	while (1)
	{
		
		char t = getch();
			switch (t)
			{
			case 72:move_y--; break;
			case 75:move_x--; break;
			case 77:move_x++; break;
			case 80:move_y++; break;
			}
			gotoxy(move_x, move_y);
			if (str[move_y][move_x] == '#')
			{
				switch (t)
				{
				case 72:move_y++; break;
				case 75:move_x++; break;
				case 77:move_x--; break;
				case 80:move_y--; break;
				}
				gotoxy(move_x, move_y);
			}
			gotoxy(1, 9);
			{
				printf("x=%d,y=%d", move_x,move_
