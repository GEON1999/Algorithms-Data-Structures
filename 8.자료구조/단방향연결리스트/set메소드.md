# set 메소드
  - index 인자와 해당 위치에 업데이트 할 value 인자를 전달 받아 업데이트함
```
class Node{
    constructor(val){
        this.val = val;
        this.next = null;
    }
}

class SinglyLinkedList{
    constructor(){
        this.head = null;
        this.tail = null;
        this.length = 0;
    }
    push(val){
        var newNode = new Node(val);
        if(!this.head){
            this.head = newNode;
            this.tail = this.head;
        } else {
            this.tail.next = newNode;
            this.tail = newNode;
        }
        this.length++;
        return this;
    }
    
    pop(){
        if(!this.head) return undefined;
        var current = this.head;
        var newTail = current;
        while(current.next){
            newTail = current;
            current = current.next;
        }
        this.tail = newTail;
        this.tail.next = null;
        this.length--;
        if(this.length === 0){
            this.head = null;
            this.tail = null;
        }
        return current;
    }
    
    shift(){
        if(!this.head) return undefined;
        // head 가 없다면 undefined 를 반환
        var currentHead = this.head;
        // 현재 head 를 currentHead 변수에 값 부여
        this.head = currentHead.next;
        // 현재 head 를 head 다음 노드로 변경
        if(this.length === 0){
            this.tail = null;
            // 마지막 노드를 지웠다면 tail 노드 값이 null 가 되도록
              // 마지막 노드의 값은 head 이자 tail 인데, 지우게 되면 다음 head 가 없음으로 null 값이 head 에 부여되지만 tail 값은 
                 //null 이 되지 않음으로 null 로 수동으로 값 부여
        }
        return currentHead;
        // 제거한 이전 head 노드 값을 반환
    }
    
    unShift(val){
        var newNode = new Node(val);
        // 전달 받은 변수로 새로운 Node 를 만들고 해당  newNode 라는 변수에 값 부여
        if(!this.head) {
            this.head = newNode;
            this.tail = this.head;
        } 
        // 리스트가 비어있는 경우, head 와 tail 의 값을  newNode 로 바꿈 
        else {
            newNode.next = this.head;
            this.head = newNode;
        }
        // 리스트가 비어있지 않은 경우, newNode 의 다음 노드의 값을 현재의 head 로 바꾸고
           //head 의 값은 newNode 로 바꿈
        this.length++;
        return this
    }
    
    get(index){
        if(index < 0 || index > this.length) return null;
        // index 가 음수이거나 list 의 길이보다 크다면 null 반환
        var count = 0;
        var currentVal = this.head;
        while(index !== count){
            currentVal = currentVal.next;
            count++;
        }
        // 전달 받은 index 인자가 count 와 같아 질 때 까지 반복되는 while 문
           //index 와 같지 않다면 currentValue 는 currentValue 다음의 노드가 되고 count 는 +1 이 됨
        return currentVal;
        //index 와 count 가 같아지는 시점에서의 currentValue 를 반환함
    }
    
    set(index, val){
        var foundNode = this.get(index);
        // get 메소드를 통해 null 혹은 해당 index 의 node 를 찾음
        if(foundNode){
            foundeNode.val = val;
            return true;
        }
        // null 이 아닌 노드를 찾은 경우 foundNode 에 해당 node 가 부여되어 있고,
        // 해당 node 의 value 를 전달받은 val 인자로 대체하고 true 를 return 함
        return false;
        // get 메소드를 통해 null 을 전달받은 경우 false 를 return 
    }
}


var list = new SinglyLinkedList()
list.push("HELLO") 
list.push("GOODBYE")
list.push("!")
```
