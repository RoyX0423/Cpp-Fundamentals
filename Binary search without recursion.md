# Cpp-prac
#Binary search in C++


#include <iostream>
using namespace std;

int main()
{
    //initializing a sorted list
     int low, mid, up,value;
     int num[10] = {87,99,210,362,466,898,909,1000,7886,9000};

     //iteration for testing use
     for (int u = 0; u < 20; u++) {


        cout << "enter the value you are looking for: " << endl;
        cin >> value;
        
        //reset the up and low for each iteration
        up = 9;
        low = 0;
        mid = (low + up) / 2;

        while (num[mid] != value && low <= up) {
            // go to lower half of current list
            if (num[mid] > value) {
                up = mid - 1;


            }
            // go to greater half of current list
            else {
                low = mid + 1;

            }
            mid = (up + low) / 2;

        }

        if (num[mid] == value) {
            cout << "item is found in the list at subscript: " << mid << endl;

        }
        else {
            cout << "item not found!" << endl;

        }
    }
    
}

