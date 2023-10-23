#include<iostream>
using namespace std;

// First Occurence
int firstOcc(int arr[],int N,int K){
    int start = 0;
    int end = N-1;
    int ans;

    int mid = start + (end-start)/2;

    while(start <= end){
        if(arr[mid] == K){
            ans = mid;
            end = mid - 1;
        }

        else if(K > arr[mid]){
            start = mid+1;
        }
        else if(K < arr[mid]){
            end = mid-1;
        }
        mid = start + (end-start)/2;
    }
    return ans;
}


// Last Occurence
int lastOcc(int arr[],int N,int K){
    int start =0;
    int end = N-1;
    int ans;

    int mid = start + (end-start)/2;

    while(start <= end){
        if(arr[mid] == K){
            ans = mid;
            start = mid + 1;
        }

        else if(K > arr[mid]){
            start = mid+1;
        }

        else if(K < arr[mid]){
            end = mid-1;
        }
        mid = start + (end-start)/2;
    }
    return ans;
}


int main(){
    int even[8] = {0,0,1,1,2,2,2,2};

    cout<<"The first occurence of 2 is : "<<firstOcc(even,8,1)<<endl;
    cout<<"The last occurence of 2 is : "<<lastOcc(even,8,1)<<endl;

    //Total No. of Occurence 
    int last = lastOcc(even,8,2);
    int first = firstOcc(even,8,2);
    int total = (last-first) + 1;

    cout<<"Total is : "<<total<<endl;

    return 0;
    
}
