# Cpp-Fundamentals
#Merge Sort
#include <iostream>
using namespace std;

void Merge(int num[], int const start, int const (mid) , int const end) {
	//initialize the length of sub arrays
	int const arrayLA = mid - start + 1;
	int const arrayLB = end - mid;


	//creating temp arrays for transferring items
	auto* leftArray = new int[arrayLA],
	    * rightArray = new int[arrayLB];

	//copying items of two halfs into temp arrays
	for (auto i = 0; i < arrayLA; i++) {
		leftArray[i] = num[start + i];
	}
	for (auto u = 0; u < arrayLB; u++) {
		rightArray[u] = num[mid + 1 + u];

	}

	//just in case the original array doesnt start from 0
	auto MergedIndex = start;
	auto arrayAindex = 0;
	auto arrayBindex = 0;

	//start merging, compare items in left and right array using the idea of selection sort

	while (arrayAindex < arrayLA && arrayBindex < arrayLB) {

		if (leftArray[arrayAindex] <= rightArray[arrayBindex]) {
			num[MergedIndex] = leftArray[arrayAindex];
			arrayAindex++;



		}
		else {
			num[MergedIndex] = rightArray[arrayBindex];
			arrayBindex++;

		}

		MergedIndex++;



	}

	//There are 3 possible source for terminating the previous while loop
	//1.arrayindexA reaches its max value singly, 2.arrayindexB to max singly, 3.both
	//when both reaches maximum,all elements are added to the merged array
	//but if only one of them did, there are some elements left in one of the sub array


	//A has some elements left
	while (arrayAindex < arrayLA) {
		num[MergedIndex] = leftArray[arrayAindex];
		arrayAindex++;
		MergedIndex++;


	}

	//OR, alternatively, B has some elements left

	while (arrayBindex < arrayLB) {
		num[MergedIndex] = rightArray[arrayBindex];
		arrayBindex++;
		MergedIndex++;


	}
	

	
}







void MergeSort(int num[],int start,int end) {

	if (start < end) {
		//when start=end, the list cannot be splitted further
		
		int mid = (start + end) / 2;
		MergeSort(num, start, mid);//further split the left half if possible
		MergeSort(num, mid + 1, end);//further split the right half if possible
		Merge(num, start, mid, end);//if no more splitting can be taken place, start sorting n merging the sub list

	
		
	}


}

void display(int num[]) {


	for (int k = 0; k <10; k++) {
		cout << num[k] << endl;
	
	
	}


}




int main()
{
	int num[10] = {21,43,22,23,42,89,86,10,4,1};

	cout << "before:" << endl;

	display(num);


	MergeSort(num, 0, 9);

	cout << "after:" << endl;

	display(num);

	

	system("pause>0");
}






