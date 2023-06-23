# 12th
#include<iostream>
#include<vector>
using namespace std;

//Q1. Sort an Array consisting 1s and 0s only

// void sortZeros(vector<int> &v){
//     int zero_count = 0;
//     for(int ele:v){// this is used to detect zeroes in the array
//         if(ele==0){
//             zero_count++;
//         }
//     }
//     for(int i=0;i<v.size();i++){
//         if(i<zero_count){
//             v[i]=0;
//         }
//         else{
//             v[i]=1;
//         }
//     }
// }
// int main() {
//     int n;
//     cin>>n;

//     vector<int> v;

//     for(int i=0;i<n;i++){
//         int ele;cin>>ele;
//         v.push_back(ele);
//     }

//     sortZeros(v);

//     for(int i=0;i<n;i++){
//         cout<<v[i]<<" ";
//     }
//     cout<<endl;
//     return 0;
// }

// Doing the above Problem with a new technique
// This is done by 2 pointer named left and right pointer 

// void sortZeros(vector<int> &v){
//     int left_p=0;
//     int right_p=v.size()-1;

//     while(left_p<right_p){
//         if(v[left_p]==1 && v[right_p]==0){
//             v[left_p++]=0;
//             v[right_p--]=1;

//         }
//         if(v[left_p]==0){
//             left_p++;
//         }
//         if(v[right_p]==1){
//             right_p--;
//         }
//     }

// }
// int main() {
//     int n;
//     cin>>n;

//     vector<int> v;

//     for(int i=0;i<n;i++){
//         int ele;cin>>ele;
//         v.push_back(ele);
//     }

//     sortZeros(v);

//     for(int i=0;i<n;i++){
//         cout<<v[i]<<" ";
//     }
//     cout<<endl;
//     return 0;
// }

// Q3. to print the even numbers of the array in the first and odd numbers in the last ofthe array'

// void sortParity(vector<int> &v){
//     int left_p=0;
//     int right_p = v.size()-1;
//     while (left_p <right_p) 
//     { 
//         if (v[left_p]%2!=0 && v[right_p]%2==0){
//             swap(v[left_p],v[right_p]);
//             left_p++;
//             right_p--;
//         }
//         if(v[left_p]%2==0){
//             left_p++;
//         }
//         if(v[right_p]%2!=0){
//             right_p--;
//         }
// }
// }
// int main() {
//     int n;
//     cin>>n;

//     vector<int> v;

//     for(int i=0;i<n;i++){
//         int ele;cin>>ele;
//         v.push_back(ele);
//     }

//     sortParity(v);

//     for(int i=0;i<n;i++){
//         cout<<v[i]<<" ";
//     }
//     cout<<endl;
//     return 0;
// }


// Q4. to return a array that have their squares sorted 


void sortedSquared(vector<int> &v){
    vector<int> ans;

    int left_p=0;
    int right_p=v.size()-1;

    while(left_p<right_p){
        if(abs(v[left_p])<abs(v[right_p])){
            ans.push_back(v[right_p]*v[right_p]);
            right_p--;
        }else{
            ans.push_back(v[left_p]*v[left_p]);
            left_p++;
        }
    }
    reverse_iterator(ans.begin(),ans.end());
    for(int i=0;i<ans.size();i++){
        cout<<ans[i]<<" ";
    }cout<<endl;
}
int main(){
    int n;
    cin>>n;
    vector<int> v;
    for(int i=0;i<n;i++){
        int ele;cin>>ele;
        v.push_back(ele);
    }

    sortedSquared(v);

    for(int i=0;i<n;i++){
        cout<<v[i]<<" ";
    }
    cout<<endl;
    return 0;
}
