/* The stock span problem is a financial problem where we have a series of n daily price quotes for a stock and we need to calculate span of stock’s price for all n days. 
The span Si of the stock’s price on a given day i is defined as the maximum number of consecutive days just before the given day, for which the price of the stock on the current day is less than or equal to its price on the given day.
For example, if an array of 7 days prices is given as {100, 80, 60, 70, 60, 75, 85}, then the span values for corresponding 7 days are {1, 1, 1, 2, 1, 4, 6} */

#include <iostream>
using namespace std;

class Stack{
    int top;
    int *arr;
    int size;
    
    public:
        
        Stack(int n){
            size = n;
            top = -1;
            arr = new int[size];
        }
        void push(int n){
            arr[++top] = n;
        }
        int pop(){
            return arr[top--];
        }
        int peek(){
            return arr[top];
        }
        bool isempty(){
            if(top == -1){
                return true;
            }
            else
                return false;
        }
};
int stockspan(Stack s, int data){
    if(s.peek()>data || s.isempty()){
        return 0;
    }
    else{
        int tmp = s.pop();
        return (1+stockspan(s,data));
        s.push(tmp);
    }
}

int main() {
	int t;
	cin>>t;
	while(t--){
	    int data;
	    int n;
	    cin>>n;
	    Stack s(n);
	    int *out = new int[n];
	    for(int i = 0; i< n; i++){
	        cin>>data;
	        s.push(data);
	        out[i] = stockspan(s,data);
	    }
	    for(int i=0; i< n; i++){
	        cout<<out[i]<<" ";
	    }
	    cout<<endl;
	}
	return 0;
}
