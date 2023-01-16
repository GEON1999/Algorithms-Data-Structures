## Object

- 정렬되어 있지 않은 데이터 구조
- key / value 로 이루어짐
- 빠른 접근, 입력 및 제거에 용이함

</br>

### Big O of Objects

- 입력**(**Insertion) - **O(1)**
- 제거**(**Removal) - **O(1)**
- 검색(Searching) - **O(N)**
    - 특정 `value` 가 객체 내 어디에 저장되어 있는지 알기 위해서는 속성들이 많을 수록 시간이 늘어남
- 접근(Access) - **O(1)**

> 위와 같이 접근, 입력 및 제거하는 시간이 상수이기에 매우 빠름
> 

</br>

### Big O of Object Methods

- Object.keys - **O(N)**
- Object.values - **O(N)**
- Object.entries - **O(N)**
- hasOwnProperty - **O(1)**
