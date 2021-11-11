# Cpp-random-prac
some basic prac code

#include <iostream>
using namespace std;

int main()
{
	int num[5] = { 5,4,3,2,1 };
	bool swap = false;
	int temp, upper;
	upper = 4;

		while (!swap) {
			swap = true;
			for (int i = 0; i < upper; i++) {
				if (num[i] > num[i + 1]) {
					temp = num[i];
					num[i] = num[i + 1];
					num[i + 1] = temp;
					swap = false;


				}

			}
			upper--;

		}
	
		//output to doublecheck if sorting works
		for (int u = 0; u < 5; u++) {
			cout << num[u] << endl;


		}

		system("pause>1");
   
}

