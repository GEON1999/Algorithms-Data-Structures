# trees
- 부모-자식 관계 정의하고, 부모자식 간에 간선이 이어져있는 그래프이다.   
- 트리는 방향성이 있는 비순환 그래프이다.

</br></br>

### tree 데이터 구조 내 용어
1. root : 제일 높은 곳에 위치한 노드(최초의 노드)
2. child : 루트 노드로부터 뻗어져 연결된 하위 노드 
3. parent : 자식 상위에 위치한 노드
4. siblings : 부모의 노드가 같은 자식 노드들
5. leaf : 더 이상 자식 노드가 없는 최하단에 위치한 노드
6. edge : 노드끼리를 이어주는 연결선

</br></br>

### tree 구조 내 rules
1. 자신보다 더 낮은 곳에 있지 않은 다른 노드와 연결될 수 없음(부모에서 자식으로만 연결 가능, 형제를 가르켜서도 안됨)
2. 루트는 단 하나임

### tree 사용처
1. HTML DOM
2. Network Routing
3. Abstract syntax tree
4. AI
5. folders in OS
6. JSON
