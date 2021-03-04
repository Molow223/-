// Разбитие строки на слова.cpp : 
#include <iostream>
#include <string>
#include <vector>

using namespace std;

// Ф-ция вектор разбивка строк
vector<string> SplitIntoWords(string text)
{
	vector<string> words;//векторы
	string word;

	//Заполнение векторов
	for (int i = 0; i < text.size(); ++i)
	{
		if (text[i] == ' ') {
			words.push_back(word);
			word = ""s;
		}
		else {
			word += text[i];
		}
	}
	words.push_back(word);
	return words; //возврвщает вектор слов
}
int main()
{
	string query;
	getline(cin, query); //считывает данные
	//цикл по коллекции
	for (string word : SplitIntoWords(query))
	{
		//Ввывод данных в консоль	
		cout << '[' << word << ']' << endl;
	}
	return 0;
}
