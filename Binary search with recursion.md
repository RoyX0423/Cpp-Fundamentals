# Cpp-prac
//binary search with recursion


#include <iostream>
using namespace std;

int binarySearch(int* num, int low, int up, int value) {
	int mid;

	if (low > up) {
		return -1;
	}
	else {


		mid = (low + up) / 2;
		if (num[mid] == value) {
			return mid;


		}
		else if (num[mid] > value) {
			return binarySearch(num, low, mid - 1, value);



		}
		else {
			return binarySearch(num, mid + 1, up, value);
		}

	}

}

int main()
{
	int num[10] = {2,5,8,10,21,33,45,77,88,99};
	int up, low,value;
	
	
	//iteration for testing use

	for (int i = 0; i < 20; i++) {
		//reset bounds
		low = 0;
		up = sizeof(num);

		cout << "enter value you are looking for: " << endl;
		cin >> value;

		int result = binarySearch(num, low, up, value);
		if (result == -1) {
			cout << "item not found!" << endl;

		}
		else {
			cout << "item found in subscript: " << result << endl;
		}
	}

	system("pause>0");
}



