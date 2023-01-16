## Array

- 데이터가 정렬되어 있음
- 정렬되어 있음으로 인해 유용할 수 있지만, 연산 시 시간이 더 소요될 수 있음
- 배열이 얼마나 긴지, 혹은 아이템이 중간에 있던 마지막에 있던지 중요하지 않음
- 데이터까지 닿는데 걸리는 시간은 상수임

</br>

### **Big O of Arrays**

- 입력**(**Insertion) - **It depends....**
    - `const names = ["Geon", "Dan"]` 에서 `Haru` 를 names 에 추가하게 되면 아래와 같이 됨
    
     `const names = ["Geon", "Dan", "Haru"]` 
    
    - 위와 같이 입력하면 걸리는 시간은 상수임. 다만, 아래와 같이 입력하면 모든 아이템의 인덱스를 수정해야함으로  **O(N)** 이됨 ****
    
    `const names = ["Haru", "Geon", "Dan"]` 
    
- 제거**(**Removal) - **It depends....**
    - 입력과 동일하게 맨 뒤에 있는 아이템을 제거하면 제거되는 시간은 상수이지만, 중간 혹은 앞에 있는 아이템을 제거할 경우 **O(N)** 이됨 ****
- 검색(Searching) - **O(N)**
- 접근(Access) - **O(1)**

> push와 pop하는 작업이 shift와 unshift 작업보다 빠름. 비어있는 배열일때만 제외
> 

</br>

### Big O of Array Operations

- push - **O(1)**
- pop - **O(1)**
- shift - **O(N)**
- unshift - **O(N)**
- concat - **O(N)**
- slice - **O(N)**
- splice - **O(N)**
- sort - **O(N * log N)**
- forEach/map/filter/reduce/etc. - **O(N)**
