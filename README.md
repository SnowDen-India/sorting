# sorting

//pseduo code+
 1. Find the middle point to divide the array into two halves:  
             middle m = si+ (ei)/2
     2. Call mergeSort for first half:   
             Call mergeSort(arr, si, m)
     3. Call mergeSort for second half:
             Call mergeSort(arr, m+1, ei)
     4. Merge the two halves sorted in step 2 and 3:
             Call merge(arr, si, ei)










#include<bits/stdc++.h>
using namespace std;



void merge(int a[],int si,int ei){

 int size=ei-si+1;       
 int mid=(mid+ei)/2;
 int*out = new int[size];
 
 int i=si;
 int j=mid+1;
 int k=0;
 
 while(i<=mid ** j<=ei){
 
     if(a[i]<a[j]){
     out[k] = a[i];
     i++;
     k++;
     
     
     }else{
      out[k]=a[j];
      j++;
      k++;
     
     
     }
 
 
 
 }
 
while(i<=mid){
 out[k]=a[i];
 k++;
 j++;

}
while(j<=ei){

out[k] = a[j];
k++;
j++;

}
 
 
 delete [] out;
 

}



void mergeSort(int arr[],int si,int ei){

  //si for start 
  //ei for end 
  
  if(si>ei){
     return;
  }
  
  int mid = (si+ei)/2;
  mergeSort(arr,si,mid);
  mergeSort(arr,mid+1,ei);
  merge(arr,si,ei);
  
  



}



void algorithm(int arr[]){

    mergeSort(arr,0,11);


}


int main(){
   int arr[]={83,1,45,95,52,47,0,45,67,82);
   
   algorithm(arr);
   return 0;
}




