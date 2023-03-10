# Big O

- 입력의 크기가 늘어날수록 전체적인 추세와 관련 되어 있음
- 입력 크기가 늘어날수록 실행 시간이 어떻게 변하는지, 혹은 공간 복잡도가 어떻게 변하는지 등
- Big O 로 측정되는 알고리즘의 시간과 공간 복잡도는 하드웨어의 영향을 받지 않음

</br>

## 좋은 코드란?

- 코드 실행 속도
- 메모리 사용량
- 코드의 가독성

</br>

### 코드의 실행 속도 측정

- `performance.now()` 를 통해 코드 실행 속도를 측정할 수 있다.
    - 다만 컴퓨터 사양등의 환경에 따라 실행속도가 상이하다
    - 컴퓨터가 같다고 해도 매번 실행속도가 일정하지 않다
    - 측정할 수 있는 수치보다 빠르게 실행되면 측정이 불가능하다

</br>

### 연산 갯수 세기

- 위와 같은 이유로 코드를 비교할 때 시간으로 측정하는 것은 힘듬
- 대신에 컴퓨터가 처리해야하는 연산 갯수를 세면 됨

</br>

## 시간 복잡도

- 입력의 크기와 실행시간의 관계의 추세만을 봄
- (f(n) =n) n 과 비례하여 시간이 늘어날 수도 있고 `O(n)`
    - `O(n * 1000 + 100)` 또한 추세를 봤을 때 n 이 커지면 실행 시간도 길어짐으로 `O(n)` 으로 표기
- (f(n) =n²) 제곱되어 시간이 늘어날 수도 있고 `O(n²)`
- (f(n) =1) n과 관계 없이 실행 시간은 늘 상수일 수도 있다. `O(1)`
    - `O(500)` 도 n 이 어떤 값이든 500이라는 상수의 결과가 나오기에 `O(1)` 로 표기
- 혹은 완전히 다를 수도 있다.

![Untitled](https://velog.velcdn.com/images/k7nsuy/post/215c40ff-4741-445e-981a-6e31ac356026/image.png)

</br>

## 공간 복잡도 (auxiliary space complexity)

</br>

### Rule

1. booleans, numbers, undefined, null은 자바스크립트에서 모두 불변 공간이다
    - boolean 이 true 던 false 던, numbers 가 100 이던 1000 이던 모두 불변의 공간이라고 여김
    - string 의 경우 다름 string 은 `O(n)` 공간이 필요함. 만약 n이 50자라면 길이가 1자인 문자보다 50배 더 큰 공간을 차지함
    - reference 타입, 배열과 객체도 같다. 대부분 O(n)이라고 생각한다
    

## log

![Untitled](https://www.mathsisfun.com/algebra/images/logarithm-concept.svg)
