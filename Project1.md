#include <tchar.h>
#include <iostream>
#include <string>
#include <ctime>
using namespace std;

int _tmain(int argc, wchar_t argv[]) // функция для всех символов кода 
{
	srand(time(NULL)); // генерация псевдослучайных чисел опираясь на дату
	setlocale(LC_ALL, "Russian"); // поддержка русского текста
	int arr[30];
	for (int i = 0; i < 30; i++)
	{
		arr[i] = rand() % 40 + 160; // заполнение массива ростом потенциальных игроков в баскетбол от 160 до 200 см
		cout << " " << arr[i]; // вывод роста всех потенциальных игроков
	}
	int s = 0;
	int r = 200;
	for (int i = 0; i < 30; i++)
	if (arr[i]>179) // рост игрока в команде должен быть не ниже 180 см
	{
		s = arr[i];
		if (s < r)
		{
			r = s; // поиск самого низкого по росту игрока принятого в команду
		}
	}
	cout << endl; // вывод
	cout << " " << r;

	cin.get(); // завершение работы с потоками
	return 0;
}