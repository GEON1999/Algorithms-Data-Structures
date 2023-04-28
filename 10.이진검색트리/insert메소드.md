## 이진 검색트리 insert 메소드

```
class Node {
    constructor(value){
        this.value = value;
        this.left = null;
        this.right = null;
    }
}

class BinarySearchTree {
    constructor(){
        this.root = null;
    }
    insert(value){
        var newNode = new Node(value);
        if(this.root === null){
            this.root = newNode;
            return this;
        }
        var current = this.root;
        while(true){
        // return 이 있을 때 까지 무한루프
            if(value === current.value) return undefined;
            // 값이 같은 경우에 대한 처리는 각각 다르지만, 여기선 값이 다를 경우는 별도 처리하지 않고 undefined 를 반환한다.
            if(value < current.value){
                if(current.left === null){
                    current.left = newNode;
                    return this;
                    // value가 current.value 보다 작은데, left 가 비어있다면 삽입
                }
                current = current.left;
                // 비어있지 않다면 current 에 current.left를 삽입하고 다시 루프 반복(비어있을 때 까지 반복)
            } else {
                if(current.right === null){
                    current.right = newNode;
                    return this;
                } 
                current = current.right;
            }
        }
    }
}
```
