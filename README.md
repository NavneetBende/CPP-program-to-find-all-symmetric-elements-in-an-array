Symmetric Elements in an Array in C++
Here, in this page we will discuss the program to find all symmetric elements in an array in C++ programming language. We are given with pairs and need to print those pairs which are symmetric.

Symmetric elements in an array
While loop in C
Method Discussed :
Method 1 : Using Naive Approach
Method 2 : Using Hash-Map
Let’s Discuss both methods one by one,

Method 1 :
Declare a 2D array for pairs.
Run a outer loop from index  0 to 5
Run an inner loop from index i+1 to 5
Check if(arr[i][0]==arr[j][1] && arr[i][1]==arr[j][0])), then print the arr[i][0] and arr[i][1].
Time and Space Complexity :
Time Complexity : O(n2)
Space Complexity : O(1)
Method 1 : Code in C++
Run
#include<bits/stdc++.h>
using namespace std;

int main ()
{
  int arr[5][2];
  arr[0][0] = 1;
  arr[0][1] = 2;
  arr[1][0] = 3;
  arr[1][1] = 4;
  arr[2][0] = 5;
  arr[2][1] = 1;
  arr[3][0] = 4;
  arr[3][1] = 3;
  arr[4][0] = 1;
  arr[4][1] = 5;

  for (int i = 0; i < 5; i++){
    for (int j = i + 1; j < 5; j++){
	  if (arr[i][0] == arr[j][1] && arr[i][1] == arr[j][0])
	    cout << "(" << arr[i][0] << ", " << arr[i][1] << ") ";
    }
  }

  return 0;

}
Output
(3, 4) (5, 1)
Related Pages
Finding Maximum scalar product of two vectors in an array

Counting the number of even and odd elements in an array

Find maximum product sub-array in a given array

Finding Arrays are disjoint or not

Determine Array is a subset of another array or not

Method 2 :
In this method we will use the map to find the symmetric pairs.

Declare an unordered_map<int, int>mp.
Run a loop from 0 to 5,
Declare two variables first = arr[i][0], second = arr[i][1].
Check if(mp.find(sec) != mp.end() and mp[sec] == first ), then print sec and first.
Time and Space Complexity :
Time Complexity : O(n)
Space Complexity : O(n)
Method 2 : Code in C++
Run
#include<bits/stdc++.h>
using namespace std;

int main ()
{
  int arr[5][2];
  arr[0][0] = 1;
  arr[0][1] = 2;
  arr[1][0] = 3;
  arr[1][1] = 4;
  arr[2][0] = 5;
  arr[2][1] = 1;
  arr[3][0] = 4;
  arr[3][1] = 3;
  arr[4][0] = 1;
  arr[4][1] = 5;

  unordered_map < int, int >mp;

  // Traverse through the given array
  for (int i = 0; i < 5; i++){
    int first = arr[i][0];
    int sec = arr[i][1];

    if (mp.find (sec) != mp.end () && mp[sec] == first)
	    cout << "(" << sec << ", " << first << ") ";

    else			// Else put sec element of this pair in hash
	mp[first] = sec;
  }

  return 0;

}
Output
(3, 4) (5, 4)
