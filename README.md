# lab01

//mokhtari, Zahra
//Tejas, Bhartiya
//07/3/2022
//This lab is being solved by a team of people
//Lab 1 this code is showing Iteration vs Recursion


#include <iostream>

// Source Code :



using namespace std;

const int SORT_MAX_SIZE = 16;

// helper function



bool isPrime (int n, int i = 2)

{

if(n== 1)

return false;

if(n == 2)

return true;

if (n % i== 0)

return false;

if (i*i> n)

return true;



// Checking for next divisor



return isPrime(n, i + 1);

}

bool IsArrayPrimelter(int *arr, int n){

cout<<"Entering IsArrayPrimelter\n";

for(int i=0;i<n;i++){

if(arr[i]==1){

cout<<"Leaving IsArrayPrimelter\n";

return false;

}

for(int j=2;j*j<=arr[i]; j++)

if(arr[i]% j == 0){

cout<<"Leaving IsArrayPrimelter\n";

return false;

}

}



  cout << "Leaving IsArrayPrimelter\n";

return true;

}

bool IsArrayPrimeRecur(int *arr, int n){

cout<<"Entering IsArrayPrimeRecur\n";

if(n==0){

cout<<"Leaving IsArrayPrimeRecur\n";

return true;

}

if(isPrime(arr[n-1])){

return IsArrayPrimeRecur(arr, n-1);

}

cout<<"Leaving IsArrayPrimeRecur\n";

return false;

}

int main(){

cout<<"Enter number of elements(max = 16): ";

int n; cin>>n;

if(n > SORT_MAX_SIZE){

cout << " INVALID INPUT!! aborting...";

return 0;

}

int *arr = new int[n];

cout << "Enter the array elements[input range : (1 to 99 inclusive)] : \n";

for (int i = 0; i < n; ++i) {

cin>>arr[i];

if(arr[i]> 99 or arr[i]<1){

cout<<"INVALID INPUT!! aborting...";

return 0;

}

}

if(IsArrayPrimelter(arr,n)){

cout<<"Prime Array using iteration\n";

}else{

cout<<"Not a Prime Array using iteration\n";

}

cout << "\n";

if(IsArrayPrimeRecur(arr,n)){

cout <<"Prime Array using recursion\n";

}else{

cout<<"Not a Prime Array using recursion\n";

}

return 0;

delete[] arr; }
