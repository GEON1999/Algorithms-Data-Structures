### stack 클래스로 구현 해보기
stack 은 후입선출의 개념을 가진 데이터 구조이기에, 배열 혹은 클래스에 중 한가지에만 적용되는 것이 아니다. 
이번엔 클래스로 구현 해보자!

- 기존의 단일 연결리스트에서의 push 와 pop 의 경우 node list 전체를 순회 후 node 를 추가하고 삭제 했기에 시간 복잡도의 효율이 좋지 않았다
- stack 데이터 구조를 활용해, push 시 node 를 맨 앞에 추가하고, pop 을 할 때도 맨 앞의 node 를 삭제하도록만 바꾸었다
```
class Node {
    constructor(value){
        this.value = value;
        this.next = null;
    }
}

class Stack {
    constructor(){
        this.first = null;
        this.last = null;
        this.size = 0;
    }
    push(val){
        var newNode = new Node(val);
        if(!this.first){
            this.first = newNode;
            this.last = newNode;
        } else {
            var temp = this.first;
            this.first = newNode;
            this.first.next = temp;
        }
        return ++this.size;
    }
    pop(){
        if(!this.first) return null;
        var temp = this.first;
        if(this.first === this.last){
            this.last = null;
        }
        this.first = this.first.next;
        this.size--;
        return temp.value;
    }
}
```
