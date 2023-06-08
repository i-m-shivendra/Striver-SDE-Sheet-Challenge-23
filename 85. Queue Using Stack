#include <stack>

class Queue {
private:
    stack<int> first;
    stack<int> second;
    
public:
    Queue() {
        // Initialize your data structure here.
    }

    void enQueue(int val) {
        first.push(val);
    }

    int deQueue() {
        if(!second.empty()){
            int data = second.top();
            second.pop();
            return data;
        }
        else{
            if(first.empty()){
                return -1;
            }
            else{
                while(!first.empty()){
                    second.push(first.top());
                    first.pop();
                }
                int data = second.top();
                second.pop();
                return data;
            }
        }
    }

    int peek() {
        if(!second.empty()){
            return second.top();;
        }
        else{
            if(first.empty()){
                return -1;
            }
            else{
                while(!first.empty()){
                    second.push(first.top());
                    first.pop();
                }
                return second.top();;
            }
        }
    }

    bool isEmpty() {
        return (first.empty() && second.empty());
    }
};
