# TBH
#include<iostream>
#include<Windows.h>
using namespace std;
/// <summary>
/// global variables
/// </summary>
string inventory[10] = { " ", " ", " ", " ", " ", " ", " ", " ", " ", " " };
int health = 100;
//funtions
int gold = 100;
void Shop();
char input;
int Mongen2();
int Mongen();
void Battlesystem();
void Battlesystem3();
void BattleSystem2();
void ItemDropper();
void Cat();
bool Haswon = false;
int main() {
	//local variables
	srand(time(NULL));//rand the seed so it changes what it give you for item dropper
	int room = 1;
	string direction;
	int milkshake = 0;
	bool chest1 = false;//have we have open teh frist chest
	bool Realend = false;
	//bool chests[5] = { 0,0,0,0,0 };//if u have alot of chest
	Beep(800, 200);
	cout << "you drive to the mouiantans but soon you see a deer you crash in to the woods" << endl;
	cout << "you wake up in a forest you can't see the beign of it nor the end of the forest you get out of your car," << endl;
	while (input != 'q' && Haswon == false && health > 0) { //////game loop
		cout << "your inventory:" << endl;
		for (int i = 0; i < 10; i++) //inventory
			cout << inventory[i] << " ";
		cout << endl << endl;

		switch (room) {
		case 1:

			system("color 0A");
			cout << "you can go (e)ast but your head feels horrible you need to escape the forest " << endl;
			cout << "you go to your nearly deystoryed trunk and open a (b)ox" << endl;
			cout << "theres a rock? " << endl;
			if (Realend == true && inventory[0] == "left dounut chunk" && inventory[1] == "donut chunk" && inventory[2] == "half a dounut") {
				cout << "why did you come back?" << endl;
				cout << "oh well your stuck now" << endl;
				cout << "you see the forest cave in on you" << endl;
				cout << "you cant see you knock out" << endl;
				cout << "you but then you wake up" << endl;
				cout << "you never left your car ur bleeding out " << endl;
				cout << "you can't move" << endl;
				input = 'q'; //end game loop
				break;
			}
			if (inventory[0] != "left dounut chunk")
				if (inventory[0] == "left dounut chunk")
					cout << "you go east" << endl;
			cin >> direction;
			if (direction == "e" || direction == "east" || direction == "E" || direction == "East")
				room = 2;
			if (direction == "r" || direction == "rock" || direction == "R" || direction == "Rock") {
				inventory[0] = "left dounut chunk";
			}
			if (direction == "b" || direction == "box" || direction == "R" || direction == "Rock") {
				if (chest1 == false) {
					cout << "the box has!" << endl;
					ItemDropper();
					chest1 = true;
				}
				else {
					cout << "the chest is empty" << endl;
				}
			}
			break;
		case 2:
			cout << "also you can go (e)ast where there is an abandoned house " << endl;
			cout << "or go back to the forest is vast you can go (w)est to the forest with your car" << endl;
			cout << "the a barrel open it?" << endl;

			cin >> direction;
			if (direction == "w" || direction == "west" || direction == "W" || direction == "West")
				room = 1;
			if (direction == "e" || direction == "east" || direction == "E" || direction == "East")
				room = 3;
			if (direction == "o" || direction == "open" || direction == "O" || direction == "Open") {
				if (inventory[1] != "dounut chunk") {
					cout << "there's a donut chunk" << endl;
					inventory[1] = "dounut chunk";
					cout << "there might be another chunk in room 5" << endl;
				}
				else { cout << "there's nothing here!" << endl; }
			}
			break;
		case 3:
			cout << " you see the abandoned house also there a (s)hop next to you can go" << endl;
			cout << "(S)outh were you see a corn field and see eyes in the corn field or you can go back west in the forest" << endl;
			cout << "theres a treasure chest in the corner (o)pen?" << endl;
			cin >> direction;
			if (direction == "w" || direction == "west" || direction == "W" || direction == "West")
				room = 2;
			if (direction == "o" || direction == "open" || direction == "O" || direction == "Open") {
				ItemDropper();
			}
			if (direction == "south" || direction == "S" || direction == "South")
				room = 4;
			if (direction == "s" || direction == "shop" || direction == "Shop") {
				Shop();
			}
			break;



		case 4:
			cout << " you're in the corn field you can go deeper (s)outh" << endl;
			cout << "but you feel like someone is staring at you also you can go back to the woods (n)orth you can " << endl;
			cout << "you can also go (e)ast in to a barn but you see a blood trail leading to it go?  " << endl;
			cin >> direction;
			if (direction == "n" || direction == "north" || direction == "N" || direction == "North")
				room = 3;
			if (direction == "e" || direction == "east" || direction == "E" || direction == "East")
				room = 5;
			if (direction == "s" || direction == "south" || direction == "S" || direction == "South")
				room = 9;
			break;
		case 5:
			cout << " your following the trail you see the barn doors open them? or go more east " << endl;
			cin >> direction;
			if (direction == "o" || direction == "open" || direction == "O" || direction == "Open") {
				BattleSystem2();
			}
			if (direction == "e" || direction == "east" || direction == "E" || direction == "East")
				room = 6;
			break;
		case 6:
			cout << " you continue east the more you head east" << endl;
			cout << "the more you walk the more you imageing blood and faces on the old withered trees" << endl;
			cout << "the faces on the trees twist in to them self soon growing taller and over shadowing you" << endl;
			cout << " you can head back by the barn going (w)est or you can go (s)outh" << endl;
			cin >> direction;
			if (direction == "w" || direction == "west" || direction == "W" || direction == "West")
				room = 5;
			if (direction == "s" || direction == "south" || direction == "S" || direction == "South")
				room = 7;
			break;



		case 7:
			cout << "you are by an old play ground" << endl;
			cout << "you feel a chill on your back the ice cold wind" << endl;
			cout << "the moon is pure white like a pearl you hear something in the bushes" << endl;
			cout << "you see a cat in the bushes (s)ee what it does?" << endl;
			cout << "you can go go north or west you see a house " << endl;
			cin >> direction;
			if (direction == "w" || direction == "west" || direction == "W" || direction == "West")
				room = 8;
			if (direction == "n" || direction == "north" || direction == "N" || direction == "North")
				room = 6;
			if (direction == "S" || direction == "see" || direction == "S" || direction == "See") {
				Cat();
			}
			break;







		case 8:
			cout << "you look into the house though the window something lunges at you or atleast trys." << endl;
			cout << "you see someone or thing? you dont know because of it mal desformties" << endl;
			cout << "you try to open the window. you were able to crack it" << endl;
			cout << "a horrible smell smacks you in the face it smells like" << endl;
			cout << "the thing in there is roiting and nobody opened the house up to let it out." << endl;
			cout << "you can go north to the barn, west to the corn field or east back to the play ground" << endl;
			cin >> direction;
			if (direction == "n" || direction == "north" || direction == "N" || direction == "North")
				room = 6;
			if (direction == "w" || direction == "west" || direction == "W" || direction == "West")
				room = 9;
			if (direction == "e" || direction == "east" || direction == "E" || direction == "East")
				room = 7;
			break;




		case 9:
			cout << " you walk though the corn field feeling a slight sense of uneasyness but you are the end of the felid go (w)est, (n)orth back to the middle of the corn felid or back to the house" << endl;
			cout << "theres a shuck of corn leaning downwards look at it?" << endl;
			cin >> direction;
			if (direction == "w" || direction == "west" || direction == "W" || direction == "West")
				room = 6;
			if (direction == "n" || direction == "north" || direction == "N" || direction == "North")
				room = 4;
			if (direction == "e" || direction == "east" || direction == "E" || direction == "East")
				room = 8;
			if (direction == "l" || direction == "look" || direction == "L" || direction == "Look") {
				if (inventory[2] != "half a dounut") {
					cout << "there's half a donut" << endl;
					inventory[2] = "half a dounut";
					cout << "you might need this" << endl;
				}
				else { cout << "there's nothing here!" << endl; }
			}
			break;
		case 10:
			cout << "you go though the corn you see an outline of a door you can walk closer? go (w)est or go to the corn field (e)ast" << endl;
			cin >> direction;
			if (direction == "w" || direction == "west" || direction == "W" || direction == "West")
				room = 7;
			if (direction == "e" || direction == "east" || direction == "E" || direction == "East")
				room = 5;
			break;

		case 11:
			cout << "You see the forest again expect now you see a door (o)pen it? or go (e)ast back to the corn field " << endl;
			cin >> direction;
			if (direction == "e" || direction == "east" || direction == "E" || direction == "East")
				room = 6;
			if (direction == "o" || direction == "open" || direction == "O" || direction == "Open")
				if (inventory[0] == "left dounut chunk" && inventory[1] == "dounut chunk" && inventory[2] == "half a dounut") {
					cout << "with the the power of a left dounut chunk,a dounut chunk and half a dounut can you open the mysterious door" << endl;
					room = 8;
				}
			break;
		case 12:
			cout << "The door opens you dont feel good your stomache twists" << endl;
			cout << "and turns you want to thorw up a breeze of the cold night wind touches you" << endl;
			cout << "smell something of roiting flesh go (e)ast? or go (n)orth back to the door " << endl;
			cin >> direction;
			if (direction == "e" || direction == "east" || direction == "E" || direction == "East")
				room = 9;
			if (direction == "n" || direction == "north" || direction == "N" || direction == "North")
				room = 7;
			break;
		case 13:
			cout << "you hate the smell you run deeper into the forest" << endl;
			cout << "you thorw up a cat come up to you to comfort you" << endl;
			cout << "(s)ee what the cat is doing, go back north, go father south or go east" << endl;
			cin >> direction;
			if (direction == "n" || direction == "north" || direction == "N" || direction == "North")
				room = 12;
			if (direction == "e" || direction == "east" || direction == "E" || direction == "East")
				room = 16;
			if (direction == "S" || direction == "see" || direction == "S" || direction == "See") {
				Cat();
			}
			if (direction == "south" || direction == "S" || direction == "South")
				room = 14;
			break;

		case 14:
			cout << "you continue south you start panicing you dont know where you are" << endl;
			cout << "all you want to do is go home" << endl;
			cout << "now it seems impossible you know you can't get out of this never ending forest" << endl;
			cout << "your so hungry and so so exshuasted you think god is playing some sick game on you well its not funny" << endl;
			cout << "you can go back north or you can go father east" << endl;
			cin >> direction;
			if (direction == "n" || direction == "north" || direction == "N" || direction == "North")
				room = 13;
			if (direction == "e" || direction == "east" || direction == "E" || direction == "East")
				room = 15;
			break;
		case 15:
			cout << "you keep wandering. you see a lake the moon shines on the lake its white like a pearl almost srereal " << endl;
			cout << " but then you hear something in the bushes maybe its the cat? (l)ook to see" << endl;
			cout << "you can go west back to the forest, east or noerth were the smell gets stornger" << endl;
			cin >> direction;
			if (direction == "w" || direction == "west" || direction == "W" || direction == "West")
				room = 14;
			if (direction == "e" || direction == "east" || direction == "E" || direction == "East")
				room = 16;
			if (direction == "n" || direction == "north" || direction == "N" || direction == "North")
				room = 18;
			if (direction == "l" || direction == "look" || direction == "L" || direction == "Look") {
				Battlesystem3();
			}
			break;
		case 16:
			cout << "the smell is getting stronger you can go north or west back to the lake" << endl;
			cin >> direction;
			if (direction == "w" || direction == "west" || direction == "W" || direction == "West")
				room = 15;
			if (direction == "n" || direction == "north" || direction == "N" || direction == "North")
				room = 17;
			break;
		case 17:
			cout << "you see blood all over the the green grass" << endl;
			cout << "next thing you know you see a fox beaten up you feel bad but its too late to save it" << endl;
			cout << "its leg is gone and its really dirty you can go west or south " << endl;
			cin >> direction;
			if (direction == "w" || direction == "west" || direction == "W" || direction == "West")
				room = 18;
			if (direction == "south" || direction == "S" || direction == "South")
				room = 16;
			break;
		case 18:
			cout << "the more you go the more you smell roiting flesh and the more blood you see" << endl;
			cout << "you can go west to the forest, north which is unknowen, south with the pond or east back to the fox" << endl;
			cin >> direction;
			if (direction == "w" || direction == "west" || direction == "W" || direction == "West")
				room = 13;
			if (direction == "n" || direction == "north" || direction == "N" || direction == "North")
				room = 19;
			if (direction == "south" || direction == "S" || direction == "South")
				room = 15;
			if (direction == "e" || direction == "east" || direction == "E" || direction == "East")
				room = 17;
			break;
		case 19:
			cout << "you see a monster you can (f)ight,(r)un" << endl;
			cout << "       .----.__" << endl;
			cout << "      /---.__  \ " << endl;
			cout << "     /       `\ |" << endl;
			cout << "    | o     o  \|" << endl;
			cout << "  ./| .vvvvv.  |\ " << endl;
			cout << " / /| |     |  | \ " << endl;
			cout << "//' | `^vvvv'  |/\\" << endl;
			cout << "~   \          |  \\" << endl;
			cout << "    |          |   ~" << endl;
			cout << "    \    |     /" << endl;
			cout << " _  |    |    |" << endl;
			cout << "   -|____|____|" << endl;
			cin >> direction;
			if (direction == "r" || direction == "run" || direction == "R" || direction == "Run")
				room = 8;
			if (direction == "f" || direction == "fight" || direction == "F" || direction == "Fight") {
				if (not Realend)
					Battlesystem();
				else
					cout << "the boss lies dead on the floor" << endl;
				if (health > 0) {
					cout << " you've defeated the boss!" << endl;
					Realend = true;
					cout << " you can go to the next room (e)ast or you back to the forest (w)est" << endl;
				}
				else if (direction == "e" || direction == "east" || direction == "E" || direction == "East")
					room = 10;
				if (direction == "w" || direction == "west" || direction == "W" || direction == "West")
					room = 8;

			}

			else {
				cout << "you died " << endl;
				break;
			}

			break;
		case 20:
			cout << "you finally see light though some bushes You escape you feel freeish but something is still missing isn't it? " << endl;
			cin >> direction;
			Haswon == true;
			break;

		}


	}//end of loop
	if (Haswon == true) {
		cout << " you see the road " << endl;
		cout << " your so exsuted you fall down" << endl;
	}

}//end of main


///funtions

void Cat() {
	int num = rand() % 100;
	if (num < 20) ///
		cout << "milkshake licks his paw" << endl;
	if (num < 80) {
		cout << " /\_/\ " << endl;
		cout << "( o.o )" << endl;
		cout << " > ^ < " << endl;
		cout << "milkshake purrs" << endl;
	}
	if (num < 60) {
		cout << " _._     _,-'""`-._" << endl;
		cout << "(,-.`._,'(       |\`-/|" << endl;
		cout << "    `-.-' \ )-`( , o o)" << endl;
		cout << "          `-    \`_`\"'- " << endl;
		cout << "milkshake has a fish" << endl;
	}
	if (num < 40) {
		cout << "   |\      _,,,---,,_" << endl;
		cout << "ZZZzz /,`.-'`'    -.  ;-;;,_" << endl;
		cout << "     |,4-  ) )-,_. ,\ (  `'-'" << endl;
		cout << "     '---''(_/--'  `-'\_) " << endl;
		cout << "milkshake is sleeping " << endl;
	}
	else
		cout << "you got nothing" << endl;


}//end of pet function

void Battlesystem() {
	system("color 1B");
	cout << " Battle commemcing" << endl;
	int MonsterHealth = 50;
	char input;
	while (health > 0 && MonsterHealth > 0) {


		if (inventory[5] != "shield") {///if you dont have the shield
			cout << " the Monster hits you for 95 Hp" << endl;
			health -= 95;
		}
		else {

			cout << " the monster hits you for 50 hp" << endl;
			health -= 50;
			Beep(800, 200);
		}
		//player acctakcs
		if (inventory[6] == "sword") {
			cout << " you hit the monster with your sword for 30 hp" << endl;
			MonsterHealth -= 50;
		}
		else {
			cout << "you punch the monster" << endl;
			MonsterHealth -= 3;
		}


		cout << " your health : " << health << ". Monster Health :" << MonsterHealth << endl;
		system("pause");
		if (health > 0 && MonsterHealth)
			cout << " you can (f)ight, (r)un, or use a (p)otion" << endl;
		cin >> input;
		if (input == 'r') {
			int num = rand() % 100;
			if (num < 80) {
				cout << " you escape the battle" << endl;
				break;
			}
			else  cout << " chance to run failed" << endl;
		}
		if (input == 'p') {
			if (inventory[2] == "\'potion\'") {
				cout << (" gulg gulg ") << endl;
				health += 35;
				inventory[2] = " ";

			}

		}// end of user input




	}// end of battle loop[
	system("pause");
}//end of funtion

void BattleSystem2() {
	int MonsterType = Mongen();
	int MonsterHealth = 0;
	int MonsterDMG = 0;
	int PlayerDMG = 0;

	// set monsters health depending on the type 
	if (MonsterType == 1) {//skeleton
		MonsterHealth = 50;
	}

	if (MonsterType == 2) { //Killer
		MonsterHealth = 50;
	}


	//set the monster's damage depending on what type
	if (MonsterType == 1) { //skeleton
		MonsterDMG = 10;
	}

	if (MonsterType == 2) { //Killer
		MonsterDMG = 65;
	}


	while (MonsterHealth > 0 && health > 0) {

		cout << "Monster bites you for " << MonsterDMG << "HP" << endl;
		health -= MonsterDMG;
		PlayerDMG = 3; //Your attack is 3

		if (inventory[6] == "sword") {
			PlayerDMG = 50;
		}
		else {
			PlayerDMG = 3;
		}
		cout << "You counter the monster for " << PlayerDMG << "HP" << endl << endl;
		MonsterHealth -= PlayerDMG;
		system("pause");
		cout << "Your health is now: " << health << endl;
		cout << "The monsters health is now: " << MonsterHealth << endl;
		system("pause");

	}
	if (MonsterHealth <= 0)
		cout << "You won!" << endl;
	else
		cout << "You died :(" << endl;
}

void Battlesystem3() {
	int MonsterType = Mongen2();
	int MonsterHealth = 0;
	int MonsterDMG = 0;
	int PlayerDMG = 0;

	// set monsters health depending on the type 
	if (MonsterType == 1) {//meat blob
		MonsterHealth = 50;
	}

	if (MonsterType == 2) { //blood shot eyeball
		MonsterHealth = 50;
	}


	//set the monster's damage depending on what type
	if (MonsterType == 1) { //meat blob
		MonsterDMG = 10;
	}

	if (MonsterType == 2) { //blood shot eye ball
		MonsterDMG = 65;
	}


	while (MonsterHealth > 0 && health > 0) {

		cout << "Monster bites you for " << MonsterDMG << "HP" << endl;
		health -= MonsterDMG;
		PlayerDMG = 3; //Your attack is 3

		if (inventory[6] == "sword") {
			PlayerDMG = 50;
		}
		else {
			PlayerDMG = 3;
		}
		cout << "You counter the monster for " << PlayerDMG << "HP" << endl << endl;
		MonsterHealth -= PlayerDMG;
		system("pause");
		cout << "Your health is now: " << health << endl;
		cout << "The monsters health is now: " << MonsterHealth << endl;
		system("pause");

	}
	if (MonsterHealth <= 0)
		cout << "You won!" << endl;
	else
		cout << "You died :(" << endl;





}


int Mongen() {
	int num = rand() % 100;
	if (num < 20) {
		cout << "you see a skeleton" << endl;
		cout << "                                _.--""-._                            " << endl;
		cout << "    .                         ."         ".                          " << endl;
		cout << "   / \    ,^.         /(     Y             |     )\                  " << endl;
		cout << "  /   `---. |--'\    (  \__..'--   -   -- -'..__/  )                 " << endl;
		cout << " |        :|    `>   '.     l_..-------.._l       .'                 " << endl;
		cout << " |      __l;__ .'      \" - .__. ^  ^      . __. - \"                " << endl;
		cout << " \  .-'  | |  `              l._  V     _.'                          " << endl;
		cout << "  \/     | |                   l`^^'^^'j                             " << endl;
		cout << "         | |                _   \_____/     _                        " << endl;
		cout << "         j |               l `--__)-'(__.--' |                       " << endl;
		cout << "         | |               | /`---``-----'\"1 | , ---- - .            " << endl;
		cout << "         | |               )/  `--' '---'   \'-'  ___  `-.            " << endl;
		cout << "         | |              //  `-'  '`----'  /  ,-'   I`.  \           " << endl;
		cout << "      _  L |_            //  `-.-.'`-----' /  /  |   |  `. \          " << endl;
		cout << "      '._' / \         _/(   `/   )- ---' ;  /__.J   L.__.\ :         " << endl;
		cout << "      `._;/7(-.......'  /        ) (     |  |            | |          " << endl;
		cout << "      `._;l _'--------_/        )-'/     :  |___.    _._./ ;          " << endl;
		cout << "        | |                 .__ )-'\  __  \  \  I   1   / /           " << endl;
		cout << "        `-'                /   `-\-(-'   \ \  `.|   | ,' /            " << endl;
		cout << "                           \__  `-'    __/  `-. `---'',-'             " << endl;
		cout << "                              )-._.-- (        `-----'      " << endl;
		cout << "                             )(  l\ o ('..-.                " << endl;
		cout << "                        _..--' _'-' '--'.-. |               " << endl;
		cout << "                __,,-'' _,,-''             \ \              " << endl;
		cout << "              f'. _,,-'                     \ \             " << endl;
		cout << "             ()--  |                         \ \            " << endl;
		cout << "              \.  |                          /  \           " << endl;
		cout << "                \ \                         |._  |          " << endl;
		cout << "                 \ \                        |  ()|          " << endl;
		cout << "                  \ \                        \  /           " << endl;
		cout << "                   ) `-.                      | |           " << endl;
		cout << "                  // .__)                     | |           " << endl;
		cout << "               _.//7'                         | |           " << endl;
		cout << "              '---'                           j_| `         " << endl;
		cout << "                                             (| |           " << endl;
		cout << "                                             |  \           " << endl;
		cout << "                                             |lllj          " << endl;
		cout << "                                             |||||          " << endl;
		return 1;
	}
	else if (num < 50) {//30% chance 20-50=30
		cout << " you see a blood shot killer" << endl;
		cout << "⠀⠀⠀     ⣀⠤⠴⠖⡒⢒⣖⣤⣀⡀⠀⠀⠀⠀⠀⡄⡀⠀⠀⠀" << endl;
		cout << "⠀⠀   ⢠⠊⠀⠀⠀⡠⠊⠁⠀⠀⠀⠀⠑⢄⠀⠀⠀⡇⠑⡄⠀⠀" << endl;
		cout << "⠀⠀   ⡆⠀⠀⠀⡌⠀⢀⡀⠀⠀⠀⣀⣀⡀⠆⠀⠀⡇⢰⠃⠀⠀" << endl;
		cout << "   ⣀⣸⡈⠁⠒⠒⠁⡊⠁⢹⡱⠀⢈⠁⢈⣿⢸⠀⠀⣇⣠⣱⠀⠀" << endl;
		cout << "  ⢀⡋⠀⣸⠀⠉⠁⠈⡆⠉⠀⢉⣤⠀⣠⣍⠉⠀⡌⢀⣦⡟⢓⠚⢲⠀" << endl;
		cout << " ⢸⠉⠀⡏⡆⠀⠀⠀⢱⠀⠀⠀⣉⠀⢈⣁⠀⡼⠀⠋⢄⠈⣏⢵⠀⠀" << endl;
		cout << " ⢸⠀⠀⡇⠘⠄⠀⠀⠀⠱⢀⠈⠛⠀⠈⡁⠌⢙⠀⡆⠈⡯⠔⡺⠀" << endl;
		cout << " ⠘⢄⡀⡇⠀⠈⠢⣀⠀⠀⠀⠈⠉⠉⠉⣠⠔⡏⠀⠈⠒⠺⠥⠇" << endl;
		cout << "    ⡇⠀⠀⠀⠀⠉⠁⠀⠀⠀⠈⠁⠀⠀⡇" << endl;
		cout << "    ⢰⠀⠀⠀⠀⠀⠀⠀⠀⣀⠔⠀⠀⠀⠃⠀" << endl;
		cout << "    ⠸⡄⠀⠀⠀⠀⡌⠉⢹⠀⠀⠀⠀⣸⠀⢀⡤⠄⠐⠒⠀⠤⡀" << endl;
		cout << "      ⠉⠀⠉⠉⠀⠀⠀⠉⠁⠀⠉⠁⠀⠀⠈⠫⠤⠤⠤⠐⠁" << endl;
		cout << " " << endl;
		cout << " " << endl;
		cout << " " << endl;
		cout << " " << endl;
		cout << " " << endl;
		return 2;
	}
	else
		cout << "nothing is there just a corpse" << endl;

}

int Mongen2() {
	int num = rand() % 100;
	if (num < 20) {
		cout << "you see a meat blob" << endl;
		return 1;
	}
	else if (num < 50) {
		cout << "blood shot eyeball" << endl;
		cout << "⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⠱⡄⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀" << endl;
		cout << "⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢸⡄⢹⠀⠀⡀⠀⠀⠀⠀⠀⠀⣇⠀⠀⠀⢀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀" << endl;
		cout << "⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⣤⣤⠴⣶⣶⣺⣿⣼⣄⠀⣟⣇⠀⢠⠀⠀⠀⣿⠀⠀⠀⡿⡆⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀" << endl;
		cout << "⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢠⠀⢀⣤⡿⠚⣹⣧⣶⠟⣏⢛⢹⣿⣿⢉⠉⡏⡿⣿⢻⠶⣤⣰⣷⡇⠠⣰⣿⣇⢀⠆⠀⠀⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀" << endl;
		cout << "⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣠⠇⠀⣸⡟⡋⢸⡆⢰⣿⣷⣄⣸⣏⣏⣹⣿⣿⡄⣸⣷⣿⣇⡟⢀⣴⣿⡟⡿⢶⣿⡟⣿⣮⣀⣠⣞⠁⠀⠀⠀⢀⣰⠃⠀⠀⠀⠀⠀⠀⠀" << endl;
		cout << "⠀⠀⠀⠀⠀⠀⠀⠀⠀⡀⠀⠀⠀⣿⣠⣞⣽⣿⡿⢿⣷⣄⣿⣟⣧⣽⣿⣟⣿⣿⣿⣟⣿⣿⣿⣿⣿⣿⣿⣿⣻⣿⠟⣼⣿⣿⣷⡟⠿⢧⣄⡀⠀⢠⣿⠃⠀⠀⠀⠀⠀⠀⠀⠀" << endl;
		cout << "⠀⠀⠀⠀⠀⠀⠀⢀⠀⢱⡄⠀⣄⣿⣿⡉⠁⢻⣿⣥⡽⢿⣻⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣷⣿⣿⣿⣿⣯⣿⣿⣯⣿⣿⣿⡿⡻⠿⣶⡾⠋⢉⣶⡿⠥⠄⣠⠞⠀⣀⠀⠀⠀⠀" << endl;
		cout << "⠀⠀⠀⠀⠀⠀⢠⠸⣆⠀⢹⣭⣿⣅⠘⣿⣾⢿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣾⣻⡯⣪⣥⡶⠛⣻⣶⣿⢏⠀⣠⣟⡁⢠⠀⢈⡀⠀⢀⠀" << endl;
		cout << "⠀⠀⠀⠀⠀⠀⣼⠀⠘⣶⣾⠏⣿⣿⢿⣿⣿⣿⣿⡿⠟⢉⣽⣿⣿⣿⠿⠛⠉⠉⠁⠀⠀⠈⠉⠉⠛⠿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣶⣾⣿⣿⣿⣷⣟⣩⣏⣹⠿⠁⣰⠃⢀⡜⠀" << endl;
		cout << "⠀⠀⠀⠀⠀⠀⢻⣥⡴⢋⣹⣿⣿⣽⣿⣿⣿⡿⠏⠀⣠⣿⣿⡿⠋⠀⠀⠀⠀⣀⣀⣤⣤⣄⣀⠀⠀⠀⠀⠈⠻⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣷⣟⣿⣶⡾⣷⣶⣾⡟⢉⣾⡇⠀" << endl;
		cout << "⠀⠀⠀⠀⠰⠂⣠⡿⣷⣾⣿⣷⣿⣿⣿⣿⠃⠀⠀⢰⣿⣿⠋⠀⠀⠀⢀⣶⣿⣿⣿⠿⠿⣿⣿⣿⣷⣄⠀⠀⠀⠈⢿⣿⣿⣻⢿⣿⣿⣿⣿⣤⣤⣾⣟⣻⣿⣿⣏⣴⡿⢋⣴⠛ " << endl;
		cout << "⠀⠀ ⠀⠀⠀⣺⣏⣾⠟⣻⣿⣿⠇⣿⣿⡇⠀⠀⢀⣿⣿⡏⠀⠀⠀⢰⣿⣿⠟⠉⠀⠀⠀⠀⠉⠻⣿⣿⣷⡀⠀⠀⠀⢻⣿⣿⢣⡙⢿⣿⣿⣿⣿⣯⣿⣶⣾⡿⣟⣭⣶⡾⠋⠀" << endl;
		cout << "  ⠠⢤⡆⣴⣳⣿⢿⣿⡿⠟⠁⠀⣿⣿⠁⠀⠀⠸⣿⣿⡇⠀⠀⠀⢸⣿⣿⣤⣤⣴⣶⣦⡀⠀⠀⠈⢿⣿⣷⠀⠀⠀⠘⣿⣿⡆⢻⠠⠟⠿⣿⣿⣿⣿⣟⡛⣻⣿⠟⠋⣀⢀⠀" << endl;
		cout << "⠀⠀⠀ ⣙⣿⣿⣿⣿⠋⣴⡄⠀⠀⣿⣿⡆⠀⠀⠀⢻⣿⣷⡀⠀⠀⠈⠻⠿⠿⠟⠛⣿⣿⣧⠀⠀⠀⢸⣿⣿⡄⠀⠀⠀⣿⣿⣇⡟⠀⠀⠀⢲⣿⣿⣿⣿⣿⣿⣶⣶⣾⡿⠟⠀" << endl;
		cout << "  ⣀⣠⣿⣟⣷⡿⢁⡾⢸⡁⠀⠀⢻⣿⣷⡀⠀⠀⠈⢿⣿⣿⣤⣀⠀⠀⠀⠀⢀⣰⣿⣿⡏⠀⠀⠀⢸⣿⣿⠁⠀⠀⢠⣿⣿⡟⠀⠀⠀⢠⣿⢿⣢⡻⢿⠙⢿⣛⣏⠁⠀⠀⠀" << endl;
		cout << " ⢠⣾⣿⠟⣽⡟⡇⠙⢿⢄⣇⠀⠀⠀⢿⣿⣷⡄⠀⠀⠀⠙⠿⣿⣿⣿⣷⣶⣿⣿⣿⡿⠋⠀⠀⠀⣠⣿⣿⡟⠀⠀⠀⣾⣿⠋⠀⠀⢀⢀⣿⡿⢷⣾⣿⣯⣄⣹⡿⠋⠀⠀⠀⠀" << endl;
		cout << "  ⠉⠁⢰⣿⠁⣳⡅⠈⣦⡝⣤⡀⠀⠈⠻⣿⣿⣦⡀⠀⠀⠀⠈⠉⠛⠛⠛⠛⠋⠁⠀⠀⠀⢀⣴⣿⣿⠟⠀⠀⢀⣾⠟⠁⠀⠀⢠⣬⣿⣿⣿⣞⠇⢳⡌⢿⣿⠁⠀⠀⠀⠀⠀" << endl;
		cout << "⠀  ⡿⢧⡀⠉⣩⣤⣧⣈⠙⠺⠶⣤⣄⡈⠻⣿⣿⣷⣦⣤⣀⡀⠀⠀⠀⠀⠀⣀⣠⣴⣾⣿⣿⠟⠁⠀⢀⣴⠟⠁⠀⢀⣤⣾⣿⣿⠿⣾⠷⣿⣆⡼⠓⣾⡇⠀⠀⠀⠀⠀⠀" << endl;
		cout << "⠀⠹⢦⣉⣉⣀⠤⡜⠉⠛⢶⣤⣄⣀⣉⡉⠛⠻⠿⠿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⡿⠿⠋⠁⣠⠴⠞⣉⣀⣀⣤⣶⢶⣻⣿⡵⣘⠢⠈⣦⠘⢿⠇⢰⡿⠁⠀⠀⠀⠀⠀⠀" << endl;
		cout << "⠀⠀⠀⠙⠛⠛⠛⢧⣤⡴⠋⠀⠈⢻⡿⠾⢿⣷⣶⣤⣴⣆⣌⣭⣉⣩⣭⣉⠀⣄⡤⣄⢠⣤⣄⣠⣴⠾⣿⡿⣏⠘⠻⣧⡘⣿⡜⠶⠄⠈⢤⠞⢠⣿⠃⠀⠀⠀⠀⠀⠀⠀" << endl;
		cout << "⠀⠀⠀⠀⣯⣭⣽⣳⢦⣉⠲⢤⣠⠏⠀⠀⡼⣱⠋⢹⣿⢻⠟⠛⡟⣿⠟⢻⠟⣟⢿⠻⣟⠛⢯⢻⣯⣆⠘⣿⡌⢳⣄⢻⣷⠈⠀⠀⢀⡤⠋⢠⡾⠃⠀⠀⠀⠀⠀⠀⠀⠀" << endl;
		cout << "⠀⠀⠀⠘⠿⠉⠉⠻⢷⣌⠙⠲⣽⡃⠀⠀⢷⠇⠀⠸⠁⡞⠀⡀⠙⡟⠂⠀⡟⢿⣼⠀⠹⡇⠈⢧⣎⢿⣇⠸⠿⠀⠉⢮⠏⠃⢀⡴⠊⠀⣠⠟⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀" << endl;
		cout << " ⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠉⠻⢦⡀⠉⠓⢦⣞⠀⠀⠀⠀⠁⠀⠀⠀⡇⠈⠳⡷⠀⡿⠴⠀⠘⠀⠸⠋⠻⣿⠀⠀⠁⠈⢈⡧⠞⠁⠀⠀⠜⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀" << endl;
		cout << "⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠁⠀⠀⠀⠉⠓⠦⣄⣀⠀⠀⠀⠁⠀⠀⠛⠀⠀⠀⠀⠀⠀⠀⠀⠀⡿⠀⠀⠀⠈⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀" << endl;
		cout << "⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠙⠓⠲⠤⢤⣀⣀⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀" << endl;
		cout << "⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠉⠉⠉⠉⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀" << endl;
		return 2;
	}
	else cout << "zombie" << endl;
}

void ItemDropper() {
	int num = rand() % 100; //0-99
	if (num < 20) {
		cout << "shield" << endl;
		inventory[5] = "shield";
	}
	else if (num < 50) {
		cout << "you got a chicken named jorge" << endl;
		inventory[5] = "chicken named jorge";
	}
	else if (num < 75) {
		cout << "you got a sword" << endl;
		inventory[6] = "sword";
	}
	else {
		cout << "you get  nothing!" << endl;
	}


}

void Shop() {
	string input = "asdfasdfsadf";
	while (input != "q") {
		cout << "welcome to the shop" << endl;
		cout << "you have $" << gold << endl;
		cout << "items for sale" << endl;
		cout << " 1) cupcake $5" << endl;
		cout << " 2) chicken  50$" << endl;
		cout << " 3) leaf 100$ " << endl;
		cout << "4) potion 10$" << endl;
		cout << " if you don't want anything (q)uit" << endl;
		cout << " what would u like to purchase" << endl;
		cin >> input;


		if (input == "1") {
			if (gold >= 5) {
				cout << " you bought the cupcake " << endl;
				inventory[8] = "cupcake";
				gold -= 5;
			}
			else
				cout << " u cant even buy a cupcake" << endl;
		}
		if (input == "2") {
			if (gold >= 50) {
				cout << " you bought the chicken " << endl;
				inventory[2] = "chicken";
				gold -= 50;
			}

			else
				cout << " u cant even buy a chicken" << endl;
		}
		if (input == "3") {
			if (gold >= 100) {
				cout << " you bought the leaf " << endl;
				inventory[3] = "leaf";
				gold -= 100;
			}

			else
				cout << " u cant even buy a leaf" << endl;
		}
		if (input == "4") {
			if (gold >= 10) {
				cout << " you bought a potion " << endl;
				inventory[4] = "potion";
				gold -= 10;
			}

			else
				cout << " u cant even buy a potion" << endl;


		}

	}
}
