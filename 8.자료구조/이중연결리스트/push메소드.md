# 이중 연결리스 push 메소드 구현

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
    }
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
    }
}

var list = new SinglyLinkedList()
list.push("HELLO")
list.push("GOODBYE")
```
