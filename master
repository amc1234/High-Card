#include <iostream>
#include <cstdlib>
#include <ctime>

using namespace std;

void checkWinner(int computer, int player, int& bank, int bet, int& highScore);
void changingBet(int& bet, int bank, int newBet);

void checkWinner(int computer, int player, int& bank, int bet, int& highScore)
{
  if (computer > player)
  {
    bank -= bet;
    cout << "Computer has highest card. Computer had " << computer << ".\n$" << bet << " is discounted from your bank. New balance: $" << bank << endl;
    if (highScore < bank)
      highScore = bank;
  }
  else
  {
    bank += bet;
    cout << "Congratulations, you have the highest card. Computer had " << computer << ".\n$" << bet << " has been added to your bank account. New balance: $" << bank << endl;
    if (highScore < bank)
      highScore = bank;
  }
}

void changingBet(int& bet, int bank, int newBet)
{
  cout << "What would you like your new bet to be?" << endl;
  cin >> newBet;

  if(newBet > bank)
    cout << "Sorry, you do not have enough funds. Operation cancelled." << endl;
  else if(newBet <=0)
    cerr << "Ivalid bet. Operation cancelled." << endl;
  else
  {
    bet = newBet;
    cout << "New bet: $" << bet << endl;
  }
}


int main()
{
  int bank = 10;
  int input = 1;
  int bet = 1;
  int highScore = 10;
  int betChanger;

  while (input == 1)
  {
    srand(static_cast<unsigned int>(time(0)));

    int computer = rand()%100 + 1;
    int player = rand()%100 + 1;

    cout << "Your card: " << player << ". Current bank funds: $" << bank << ". Current bet: $" << bet << ". Change bet?" << endl;
    cout << "1-yes \n2-no"<< endl;
    cin >> betChanger;

  /*  while (betChanger != 1 || betChanger != 2)
    {
      cerr << "Error: invalid response. Please try again." << endl;
      cin >> betChanger;
    }*/

    if(betChanger == 1)
      changingBet(bet, bank, 0);

    checkWinner(computer, player, bank, bet, highScore);
    if (bank <= 0)
    {
      cout << "Bank balance is $0, you have no more funds. Game over." << endl;
      cout << "High Score was: " << highScore << ". Thanks for playing!" << endl;
      return 0;
    }

    cout << "Continue playing?" << endl;
    cout << "1-yes \n2-no"<< endl;
    cin >> input;

  /*while (input != 1 || input != 2)
    {
      cerr << "Error: invalid response. Please try again." << endl;
      cin >> input;
    }*/
  }

  cout << "High Score was: " << highScore << ". Thanks for playing!" << endl;
  return 0;
}
