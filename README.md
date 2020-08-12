//Purpose: Heapsort
//Programming language used: C++
#include<iostream> 
#include<string>
using namespace std; 

void maxHeap(int [], int, int);
void heapSort(int [], int);
int main() 
{ 
    int n;
    cout<<"Number of elements in the heap: ";
    cin>>n;
    int array[n];
    cout<<"Enter "<<n<<" keys:"<<endl;
  for(int i=0;i<n;i++)
  {
      cin>>array[i];
  }
  
    heapSort(array, n); 
  
    cout << "The sorted list is \n"; 
 for (int i = 0; i < n; i++) 
        cout << array[i] << " "; 
    cout << endl;
} 

void heapSort(int array[], int n) 
{ 
    //to go over all the nodes.
    for (int i = n / 2 - 1; i >= 0; i--) 
        maxHeap(array, n, i); 


    for (int i = n - 1; i >= 0; i--) { 
        swap(array[0], array[i]); 
  
  //recursive call
        maxHeap(array, i, 0); 
    } 
} 

void maxHeap(int array[], int n, int i) 
{ 
    int largest = i; 
    int child1 = 2 * i + 1; 
    int child2 = 2 * i + 2; 
  
    if (child1 < n && array[child1] > array[largest]) 
        largest = child1; 
   
    if (child2 < n && array[child2] > array[largest]) 
        largest = child2; 
  
  //if largest value is changed
    if (largest != i)
    { 
       int  temp=array[i];
        array[i]=array[largest];
        array[largest]=temp; 
    
        maxHeap(array, n, largest); 
    } 
} 
  
