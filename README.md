# implement_circular_queue
class MyCircularQueue {

    int []q;
    int front=0,rear=0,size=0;
    MyCircularQueue(int k) {
        q=new int[k];
        Arrays.fill(q,-1);
    }
    
    public boolean enQueue(int value) {
        if(isFull()){
            return false;
        }
        if(isEmpty()){
            rear=front=0;
            q[rear]=value;
            size++;
            return true;
        }
        
        rear++;
        size++;
        rear=rear%q.length;
        q[rear]=value;
        return true;
        
        
    }
    
    public boolean  deQueue() {
        if(isEmpty()){
            if(isEmpty())
                return false;
        }
        q[front]=-1;
        size--;
        front++;
        front=front%q.length;
        return true;
    }
    
    int Front() {
        return q[front];
    }
    
    int Rear() { 
        return q[rear];
    }
    
    public boolean  isEmpty() {
        return size==0;
    }
    
    public boolean isFull() {
        return size==q.length;
    }
};

/**
 * Your MyCircularQueue object will be instantiated and called as such:
 * MyCircularQueue* obj = new MyCircularQueue(k);
 * bool param_1 = obj->enQueue(value);
 * bool param_2 = obj->deQueue();
 * int param_3 = obj->Front();
 * int param_4 = obj->Rear();
 * bool param_5 = obj->isEmpty();
 * bool param_6 = obj->isFull();
 */
