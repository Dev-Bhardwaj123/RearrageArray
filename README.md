# RearrageArray
Rearrange the array in such a way that the n th largest and n th smallest number are consecutive.
//Given an array rearrange in in such a way that n th largest and n the smallest are consecutive
// Ex: {1,2,3,4,5,6} ==> {6,1,5,2,4,3}
#include<iostream>
#include<bits/stdc++.h>
using namespace std;

int main(){
	int n;
	cout<<"Enter a number: ";
	cin>>n;
	int arr[n];
	for(int i=0;i<n;i++)
	{
		cin>>arr[i];
	}
	int grr[n];
	for(int i=0;i<n;i++){
		grr[i]=arr[i];
	}
	sort(grr,grr+n); //arr in increasing order
	int sm[n];
	for(int i=0;i<n;i++){
		sm[i]=grr[n-i-1]; //arr in decreasing order
	}
	int arranged[n];
	int j=0,k=0;
	for(int i=0;i<n;i++){
		if(i%2==0){
			arranged[i]=sm[j];
			j++;
		}
		else{
			arranged[i]=grr[k];
			k++;
		}
	}
	cout<<"Rearranged array is: ";
	for(int i=0;i<n;i++){
		cout<<arranged[i]<<" ";
	}
	return 0;
	
}
