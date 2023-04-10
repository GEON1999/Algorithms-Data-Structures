# unshift 메소드
  - unshift 메소드는 전달받은 변수를 맨 앞에 추가하고 새로운 길이를 반환한다. 
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
                 null 이 되지 않음으로 null 로 수동으로 값 부여
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
           head 의 값은 newNode 로 바꿈
        this.length++;
        return this
    }
}

var list = new SinglyLinkedList()
list.push("HELLO") 
list.push("GOODBYE")
list.push("!")
```
