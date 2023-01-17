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

## 이분탐색의 시간복잡도 
이분탐색이란, 정렬된 배열에서 특정 값을 찾는 탐색 알고리즘이다. 배열의 중간을 기준으로 데이터를 탐색하기 때문에 반드시 데이터가 정렬된 상태로 존재해야 한다. 
이진 탐색의 시간 복잡도는 O(logN)으로 배열을 전수 조사하는 O(N)에 비하면 상대적으로 빠른 탐색 알고리즘에 속한다. O(logN)만에 값을 찾을 수 있는 이유는 중간을 기준으로 탐색 대상을 절반씩 줄여나가기 때문이다.

전체 데이터의 수를 N이라고 하자.

1) 첫 번째 탐색 후 절반만 남아 남은 수가 $N/2$개.

2) 두 번째 탐색에서 다시 절반만 남아 남은 수가 $N/2×1/2$개.

3) 세 번째 탐색에서 다시 절반이 남아 남은 수가 $N/2×1/2×1/2$개.

k) 규칙을 찾아보면 k번째 탐색에서 남은 데이터 수는 $(1/2)^k×N$이 된다.

최악의 경우에선 $(1/2)^k×N=1$이 될 때까지 탐색을 하게 됨을 다시 한 번 기억하자.

위 식의 양변에  $2^k$를 곱하면 $2^k=N$가 되고 다시 양변에 $log2$를 취하면 최종 식은
 $k=log2N$이 된다.

여기서 k는 탐색 횟수로 N에 따라 시행 횟수는 $logN$이 된다. 따라서 시간 복잡도는 $O(logN)$으로 나타낼 수 있다.
log2 → log10의 2 아니고 log2

![11111](https://user-images.githubusercontent.com/99253403/212901439-c2c0410a-1bef-491a-822e-a0279fb2be0c.png)

![image](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/90a64c54-15a1-4341-ba6c-875706df9eb1/img.gif?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20230117%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20230117T123939Z&X-Amz-Expires=86400&X-Amz-Signature=ee3ad338e4a28250dd2a95efcbbd4df565f02d8c20194925c2bc65d4b4f21128&X-Amz-SignedHeaders=host&response-content-disposition=filename%3D%22img.gif%22&x-id=GetObject)



## 참고자료
* https://coding-factory.tistory.com/609
* https://madplay.github.io/post/time-complexity-space-complexity
* https://blog.chulgil.me/algorithm/
* https://hanamon.kr/%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98-time-complexity-%EC%8B%9C%EA%B0%84-%EB%B3%B5%EC%9E%A1%EB%8F%84/
