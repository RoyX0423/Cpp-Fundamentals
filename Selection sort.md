# Cpp-Fundamentals
#Selection sort


#include <iostream>
using namespace std;


int main()
{
	int num[10] = {90,289,22,11,91,21,9,3,1,2};
	int lower = 0;
	int index,min;
	

	while (lower != 9) {
		//reset min and index in case it does not jump into the IF inside FOR
		min = num[lower];
		index = lower;
		for (int i = lower+1; i < 10; i++) {

			if (num[i] < min){
			  min = num[i];
			  index = i;
			}
		}
		//swapping elements as required
		num[index] = num[lower];
		num[lower] = min;	
		lower++;



	}

	for (int u = 0; u < 10; u++) {
		cout << num[u] << endl;
	}

	system("pause>0");
}






