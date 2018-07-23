#include <iostream>
#include <windows.h>
#include <conio.h>





int main()
{
    COORD position;
 //   setlocale(LC_ALL, "Rus");//задание кодировки
 //   system("mode con cols=100 lines=45");//задание размеров окна консоли
 //   system("title Space Invader");//задание описания окна консоли
 //   system("color 0C");//задание цвета консоли (0-задний фон; А-передний фон)
    HANDLE hCons = GetStdHandle(STD_OUTPUT_HANDLE);//получение хендла
//    CONSOLE_CURSOR_INFO cursor = { 100, false };//число от 1 до 100 размер курсора в процентах; false\true - видимость
//    SetConsole CursorInfo(hCons, &cursor);//применение заданных параметров курсора
    int b;

    position.X = 0;
    position.Y = 0;

    do{
    SetConsoleCursorPosition(hCons, position);
          b = getch();
          if (b == 224){
            b = getch();
          }
          if (b == 72){//up
            position.Y--;
          }
          if (b == 80){//down
            position.Y++;
          }
          if (b == 75){//left
            position.X--;
          }
          if (b == 77){//right
            position.X++;
          }

        std::cout << '#';
//        system("cls");
//        Sleep(100);
    }
    while (b != 113 && b != 169);


    return 0;
}
