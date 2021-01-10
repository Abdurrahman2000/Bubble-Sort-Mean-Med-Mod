# Bubble-Sort-Mean-Med-Mod

Due to / being integer division sometimes value for average and med show as integers instead of decimal answers regardless of the float data type,

#include <stdio.h>

void swap (int *x,int *y){
    int tp=*x;
    *x=*y;
    *y=tp;
}

void bubble_sort(int arr[],int n){
    int i,j;
    
    for(i=0;i<n-1;i++){

    for(j=0;j<n-i-1;j++){
    
    if(arr[j]>arr[j+1])
        swap(&arr[j],&arr[j+1]);}
    }
}

void p_arr(int arr[],int s){
    int i;
    for (i=0;i<s;i++)
    printf("%d ",arr[i]);
    printf("\n");
}

void avg(int arr[],int s){
    int i;
    float sum,avg;
    sum=0;
    for(i=0;i<s;i++){
        sum=sum+arr[i];
    }
    avg=sum/s;
    printf("Average :%10.1f\n",avg);
}

void mediun(int arr[],int s){
    int b;
    float m;
    if(s%2!=0){
    b=(s/2);
    printf("Mediun = %d\n",arr[b]);
    }
    else{
    b=s/2;
    m=(arr[b]+arr[b-1])/2;
    printf("Mediun - (%d+%d)/2 = %10.1f\n",arr[b],arr[b-1],m);    
    }
}

void mode(int arr[],int n){
    int md,c,tc;
    c=0;
    for(int s=0;s<n;s++){
        tc=0;
    for(int i=0;i<n;i++){
        if (arr[s]==arr[i])
        tc++;
      if (tc>c){
      c=tc;
      md=arr[s];
      }
    }
}
 printf("Most frequent element - %d\nRepetitions - %d",md,c);
 
}

void main(){
    int c,n;
    printf("Number of elements you would like in your number list - ");
    scanf("%d",&n);
    int l[n];
    for(c=0;c<n;c++){
        printf("Term %d = ",(c+1));
        scanf("%d",&l[c]);
    }
    printf("Before sorting ;\n");
    p_arr(l,n);
    bubble_sort(l,n);
    printf("After sorting ;\n");
    p_arr(l,n);
    avg(l,n);
    mediun(l,n);
    mode(l,n);
}

