### 이중 연결리스트 set 메소드
- 전달 받은 index 에 위차한 노드의 값과 val 의 값을 바꿈

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
    },

    unshift(val){
        var newNode = new Node(val)
        if(!this.head){
            this.head = val;
            this.tail = val;
        } else {
            this.head.prev = newNode;
            newNode.next = this.head;
            this.head = newNode;
        }
        this.length++;
        return newNode;
    },

    get(index){
        if(index > 0 || index > this.length) return undefined;
        if(index > this.length / 2){
            // 받은 index 가 list 의 length 를 반으로 나눈 값 보다 크다면
            // 즉 index 가 tail 의 값과 가깝다면 뒤에서 부터 prev 를 통해 찾음
            var count = this.length - 1;
            // index 값이기에 -1
            var currentVal = this.tail;
            while(currentVal !== index){
                currentVal = currentVal.prev;
                count--;
            }
        } else {
            var count = 0;
            var currentVal - this.head;
            while(currentVal !== index){
                currentVal = currentVal.next;
                count++
            }
        }
        return currentVal
    },

    set(index, val){
        var foundNode = this.get(index);
        if(foundNode != null){
            foundNode.val = val;
            return true;
        }
        return false;
    },
    
    insert(index, val){
         // 단일 연결리스트와 매우 유사하나, next 뿐 아니라 prev 도 연결 해야하는 것이 다르다
        if(index < 0 || index > this.length) return false;
        if(index === 0) return !!this.unshift(val);
        if(index === this.length) return !!this.push(val);

        var newNode = new Node(val);
        var beforeNode = this.get(index-1);
        var afterNode = beforeNode.next;

        beforeNode.next = newNode, newNode.prev = beforeNode;
        newNode.next = afterNode, afterNode.prev = newNode;
        this.length++;
        return true;
  }
}
```
