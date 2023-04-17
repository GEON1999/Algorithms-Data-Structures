# 이중 연결리스 shift 메소드 구현

```
class Node{
    constructor(val){
        this.val = val;
        this.next = null;
        this.prev = null;
    }
}

class DoublyLinkedList{
    constructor(){
        this.head = null;
        this.tail = null;
        this.length = 0;
    },
    push(val){
        var newNode = new Node(val);
        if(this.length === 0){
          this.head = newNode;
          this.tail = newNode;
        } else {
          this.tail.next = newNode;
          newNode.prev = this.tail;
          this.tail = newNode;
        }
        this.length++;
        return this;
    },
    
    pop(){
        if(this.head = null) return undefined;
        var poppedNode = this.tail;
        if(this.length === 1){
            this.head = null;
            this.tail = null;
        } else{
            this.tail = this.tail.prev;
            this.tail.next = null;
            // tail.next 를 null 롤 설정하지 않으면, tail.next 시 poppedNode 가 값이 남아있게 된다.
            poppedNode.prev = null;
            // poppedNode.prev 를 null 로 설정하지 않으면, var oldTail = list.pop() 시 oldTail 에 poppedNode 값이 들어가고,
            // poppedNode.prev 를 하면 이전 값이 연결되어 
        }
        this.length--;
        return poppedNode;
    },
    
    shift(){
        if(this.head = null) return undefined;
        var shiftedNode = this.head;
        if(this.length === 1){
            this.head = null;
            this.tail = null;
        } else {
            this.head = this.head.next;
            this.prev = null;
            shiftedNode.next = null;
        }
        this.length--;
        return shiftedNode;
    }
    
}
```
