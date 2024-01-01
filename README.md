# Quicksort
Quicksort is better than merge sort of input size is less
#include <stdio.h>
```
void swap(int a[],int i,int j)
{
    int t=a[i];
    a[i]=a[j];
    a[j]=t;
}
int partition(int a[],int p,int r)
{
    int x=a[r];
    int j,i=p-1;
    for(j=p;j<=r-1;j++)
    {
        if(a[j]<=x)
        {
            i=i+1;
            swap(a,i,j);
        }
    }
    swap(a,i+1,r);
    return i+1;
}
void quicksort(int a[],int p,int r)
{
int q;
    if(p<r)
    {
        q=partition(a,p,r);
        quicksort(a,p,q-1);
        quicksort(a,q+1,r);
    }
}
void display(int a[],int n)
{
    for(int i=0;i<=n;i++)
        printf("%d\t",a[i]);
}

int main() 
{
int a[]={6,3,9,1,30,5,8,4,7};
int size=sizeof(a)/sizeof(a[0]);
int p=0;
printf("%d\n",size);
quicksort(a,p,size-1);
display(a,size-1);
    return 0;
}
```
