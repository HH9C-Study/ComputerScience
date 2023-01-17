# 복잡도
* 복잡도는 `시간복잡도`와 `공간복잡도`로 나뉜다.

## 시간복잡도 ⏰ Time Complexity

* 시간복잡도와 빅오표기법에 대해 공부해보자 ➡ 
[시간복잡도 Time Complexity](https://hanamon.kr/%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98-time-complexity-%EC%8B%9C%EA%B0%84-%EB%B3%B5%EC%9E%A1%EB%8F%84/)
* 시간복잡도의 존재 이유 ➡ 효율적인 코드로 개선하는데 쓰이는 척도가 됨
* O(n^2) 보다는 O(n) 보다는 O(1)을 지향해야 한다.
* 성우님이 주신 추가 자료 [시간복잡도 Big-O(빅오)란?](https://ssdragon.tistory.com/100)

## 공간복잡도 📁 Space Complexity
* 공간복잡도는 프로그램을 실행시켰을 때 필요로하는 자원 공간의 양을 말한다.
* 정적 변수로 선언된 것 말고도, 동적으로 재귀적인 함수로 인해 공간을 계속 필요로 할 경우도 포함된다.
* 총 공간 요구 = 고정 공간 요구 + 가변 공간 요구로 나타낼 수 있으며 수식으로는 $ S(P) = c+S_{P}(n) $ 으로 표기한다.
* 고정 공간은 입력과 출력의 횟수나 크기와 관계없는 공간의 요구(코드 저장 공간, 단순 변수, 고정 크기의 구조 변수, 상수)를 말한다.
* 가변 공간은 해결하려는 문제의 특정 인스턴스에 의존하는 크기를 가진 구조화 변수들을 위해서 필요로 하는 공간, 함수가 순환 호출을 할 경우 요구되는 추가 공간, 그러니까 동적으로 필요한 공간을 말한다.

## 자료 구조에서의 시간복잡도
| 자료구조                           | 접근       | 탐색      | 삽입      | 삭제      |
|:-------------------------------|:---------|:--------|:--------|:--------|
| 배열(array)                      | O(1)     | O(n)    | O(n)    | O(n)    |
| 스택(Stack)                      | O(n)     | O(n)    | O(1)    | O(1)    |
| 큐(queue)                       | O(n)     | O(n)    | O(1)    | O(1)    |
| 이중 연결 리스트(doubly linked list)  | O(n)     | O(n)    | O(1)    | O(1)    |
| 해시테이블 (hash table)             | O(n)     | O(n)    | O(n)    | O(n)    |
| 이진 탐색 트리 (BST)                 | O(n)     | O(n)    | O(n)    | O(n)    |
| AVL 트리                         | O(logn)  | O(logn) | O(logn) | O(logn) |
| 레드 블랙 트리                       | O(logn)  | O(logn) | O(logn) | O(logn) |



## 참고자료
* https://coding-factory.tistory.com/609
* https://madplay.github.io/post/time-complexity-space-complexity
* https://blog.chulgil.me/algorithm/
* https://hanamon.kr/%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98-time-complexity-%EC%8B%9C%EA%B0%84-%EB%B3%B5%EC%9E%A1%EB%8F%84/
