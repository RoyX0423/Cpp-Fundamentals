# Cpp-prac
//insertion sort 

#include <iostream>
using namespace std;

int main()
{
	//insertion sort in ascending order
	int num[5] = { 5,4,3,2,1 };
	int thisNum, thisIndex;

	for (int i = 1; i < 5; i++) {
		thisNum = num[i];
		thisIndex = i;
			while (num[thisIndex - 1] > thisNum && thisIndex > 0) {
				num[thisIndex] = num[thisIndex - 1];
					thisIndex--;
			
			
			}

			//insertion point was founded
			num[thisIndex] = thisNum;

	
	
	}
	//output the sorted array
	for (int u = 0; u < 5; u++) {
		cout << num[u] << endl;
	
	
	
	}


		system("pause>1");
   
}

