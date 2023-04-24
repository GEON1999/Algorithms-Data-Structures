### queue
스택과 반대로 선입선출의 형태를 가진 데이터 구조이다.   
게임등에 접속 시 대기가 있다면, 먼저 접속을 시도한 유저부터 입장하게 되는데, 이러한 데이터 구조를 연상하면 이해가 쉽다.  

- array 에서 push를 하고 shift 를하거나, 혹은 unshift 를 하고 pop 을 하면 이러한 구조가 된다. 
  - 다만, array 에서는 index 를 가지고 있기에 push 후 shift 를 하면 index 가 다 밀리게 되고, 시간복잡도나 메모리의 효율이 나빠지게 된다.(unshift 도 제일 앞에 삽입하는 것이기에 효율적이지 않다)
- class 를 활용하면 삽입과 제거 시에 시간복잡도를 상수로 둘 수 있다. 
  - 단일연결리스트에서의 push 와 shift 의 모습과 거의 동일하다.
  - 삽입을 앞에서부터 뒤로하고 맨 앞에서부터 제거하는 방법과 뒤에서 앞으로 삽입하고 맨 뒤에서 제거하는 방법이 있다.
  - 뒤에서부터 앞으로 node 를 쌓으면, 제거 시 단일연결리스트의 경우 nodelist 를 모두 순회해야하기에 비효율적이다. 그럼으로 push 와 shift 의 방식을 사용하는 것이 좋다.

```
class Node {
    constructor(value){
        this.value = value;
        this.next = null;
    }
}

class Queue {
    constructor(){
        this.first = null;
        this.last = null;
        this.size = 0;
    }
    enqueue(val){
        var newNode = new Node(val);
        if(!this.first){
            this.first = newNode;
            this.last = newNode;
        } else {
            this.last.next = newNode;
            this.last = newNode;
        }
        return ++this.size;
    }

    dequeue(){
        if(!this.first) return null;

        var temp = this.first;
        if(this.first === this.last) {
            this.last = null;
        }
        this.first = this.first.next;
        this.size--;
        return temp.value;
    }
}
```
