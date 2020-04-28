# get-max-element-from-stack
#include <iostream>
#include<stack>
using namespace std;
int maxe;
void push_(stack<int>&s,int k)
{
    if(s.empty())
    {
        maxe=k;
        s.push(k);
        
    }
    else if(maxe>k)
    {
    s.push(k);
    }
    else
    {
        s.push(maxe+k);
        maxe=k;
    }
}
void pop_(stack<int>&s)
{
    if(s.empty())
    return;
    else if(s.top()<maxe)
    s.pop();
    else
    {
        maxe=s.top()-maxe;
        s.pop();
    }
}
int max_()
{
    cout<<maxe<<endl;
}
int main() {
	int n;
	cin>>n;
	maxe=0;
	stack<int>s;
	while(n--)
	{
	    string str;
	    int u;
	    cin>>str;
	    if(str=="push")
	    {
	        cin>>u;
	        push_(s,u);
	        
	    }
	    else if(str=="pop")
	    pop_(s);
	    else if(str=="max")
	    max_();
	}
	return 0;
}
