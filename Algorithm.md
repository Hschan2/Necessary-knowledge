# Algorithm (알고리즘)

## 코딩 테스트를 위한 팁
### 1. 칠판에 글쓰기
관련성이 있는 그림을 생각하면서 그림을 그린다. 알고 있는 알고리즘의 명제를 적어두고 알고리즘 연습을 한다.

### 2. 이야기하기
자신이 한 말을 두려워하지 말고 말하는 것이 좋다. 문제를 생각하는 것에 그치지 말고 해결 과정에서 막혔다면 말하면서 푸는 방법도 좋다. 가끔 면접 상황에서 명확하게 말하는 것이 현재 문제에서 무슨 일이 일어나고 있는지 이해할 수 있다.

### 3. 알고리즘 생각하기
문제의 세부 사항을 검토하고 해결책이 나올 것을 기대하는 것이 유용하다. (상향식 접근법) 다른 알고리즘에 대해서도 생각해 볼 수 있으며 알고리즘이 문제에 적용이 되는지 생각할 수 있다. (하향식 접근법)

#### 문제의 해결에 도움이 되는 알고리즘 기법
* Sorting (Plus searching, Binary search)
* Divide and Conquer
* Dynamic Programming, Memoization
* Greediness
* Recursion
* Algorithms associated with a specific data structure (which brings us to our fourth suggestion)

### 4. 데이터 구조 생각하기
상위 10개의 데이터 구조가 실제 사용되는 모든 데이터 구조의 99%를 차지한다. 때로는 최적의 솔루션이 블룸 필터 또는 접미어 트리를 필요로 하는 문제를 묻는다. 하지만 이러한 문제도 훨씬 더 일상적인 데이터 구조를 사용하는 최적의 솔루션을 사용할 때가 있다.

#### 자주 표시될 데이터 구조
* Array
* Stack, Queue
* HashSet, HashMap, HashTable, Dictionary
* Tree, Binary tree
* Heap
* Graph

### 5. 이전의 관련 문제와 해결 방법에 대해 생각하기
현재 제시된 문제는 이전에 보았던 문제들과 비슷할 것이다. 솔루션에 대해 생각해보고 문제의 세부 사항에 어떻게 적용할 수 있는지 생각한다. 문제가 제기되는 형태로 넘기지 말고 핵심 과제로 넘어가서 과거에 해결한 것과 일치하는지 확인한다.

### 6. 문제를 작은 문제로 분해하여 수정하기
특별한 경우나 문제의 단순화된 버전으로 해결한다. 문제의 복잡성과 범위를 제한하는 것으로 좋은 방법이 될 수 있다.문제를 큰 문제의 하위 집합으로 축소하면 작은 부분부터 시작하여 전체 범위까지 작업을 진행할 수 있다. 작은 문제의 구성으로 문제를 보는 것이 큰 도움이 될 수 있다.

### 7. 접근을 되돌아 오는 것을 두려워하지 말기
특정 접근법이 효과적이지 않았다면 다른 접근법을 시도할 때가 있다. 그렇다고 쉽게 포기할 필요는 없다. 그러나 더 이상 생각이 떠오르지 않는다면 다시 되돌아가서 새로 시작한다.   

## 문제 해결을 위한 전략적 접근
### 코딩 테스트 목적
* 문제 해결 여부
* 예외 상황과 경계값 처리
* 코드 가독성과 중복 제거 여부 등 코드 품질
* 언어 이해도
* 효율성   

궁극적으로 문제 해결 능력을 보기 위함이며 "어떻게 이 문제를 창의적으로 해결할 것인가?"를 측정하기 위함으로 볼 수 있다.   

### 접근 방식
* 문제를 공격적으로 받아들이고 필요한 정보를 추가적으로 요구해 해당 문제에 대해 완벽하게 이해하기
* 문제를 익숙한 용어로 재정의 혹은 해결하기 위한 정보를 추출하는 것을 추상화
* 추상화된 데이터를 기반으로 문제를 어떻게 해결할 지 계획한다. 이 때, 사용할 알고리즘과 자료구조를 고민한다.
* 계획에 대해 검증한다. 수도 코드 작성도 해당될 수 있고 문제 출제자에 의견을 물어볼 수 있다.
* 계획으로 문제를 해결한다. 해결이 되지 않는다면 앞 과정을 되짚어본다.   

### 생각하는 방식
* 비슷한 문제를 생각한다.
* 단순한 방법으로 시작하여 점진적으로 개선한다.
* 작은 값을 생각한다.
* 그림을 그려본다.
* 수직으로 표현해본다.
* 순서를 강제해본다.
* 뒤에서부터 생각해본다.   

## 해결 방법 분류
### DP (동적 해결법)
복잡한 문제를 간단한 여러 개의 하위 문제 (Sub-problem)로 나누어 푸는 방법이다.   

<b>DP 구현 방식 두 가지</b>   

* Top-down: 여러 개의 하위 문제를 나눴을 때, 하위 문제를 결합하여 최종적으로 최적 해를 구한다.
    * 같은 하위 문제를 가지고 있는 경우 존재한다. 해당 최적 해를 저장해서 사용하는 경우, 하위 문제 수가 기하급수적으로 증가할 때 유용하다. (Memoization 방법)
* Bottom-up: Top-down 방식과 반대로 하위 문제들로 상위 문제의 최적 해를 구한다.   

피보나시 수열로 예를 들어서
```
Top-down

f (int n) {
    if n == 0: return 0
    elif n == 1: return 1
    if dp[n] has value: return dp[n]
    else: dp[n] = f(n-2) + f(n-1)
            return dp[n]
}
```

```
Bottom-up

f (int n) {
    f[0] = 0
    f[1] = 1
    for (i = 2; i <= n; i++) {
        f[i] = f[i-2] + f[i-1]
    }
    return f[n]
}
```

#### 접근 방법
* 모든 답을 만들어보고 그 중 최적 해의 점수를 반환하는 완전 탐색 알고리즘을 설계
* 전체 답의 점수를 반환하는 것이 아닌 앞으로 남은 선택들에 해당하는 저수만을 반환하도록 부분 문제 정의를 변경
* 재귀 호출의 입력 이전의 선택에 관련된 정보가 있다면 필요한 것만 남기고 축소
* 입력이 배열이거나 문자열인 경우에 가능하다면 적절한 변환을 통해 Memoization할 수 있도록 조정
* Memoization 적용   

### Greedy (탐욕법)
모든 선택지를 골라보고 그 중 가장 좋은 것을 찾는 방법이 Divide Conquer or DP 였다면 Greedy는 각 단계마다 지금 당장 가장 좋은 방법만을 선택하는 해결 방법이다. 탐욕법은 동적 계획법보다 수행 시간이 훨씬 빠르기 때문에 유용하다. 많은 경우 최적 해를 찾지 못하고 적용될 수 있는 경우가 두 가지로 제한된다.   

* 탐욕법을 사용해도 항상 최적 해를 구할 수 있는 경우
* 시간이나 공간적 제약으로 최적해 대신 근사해를 찾아서 해결하는 경우   

#### 접근 방법
* 문제의 답을 만드는 과정을 여러 조각으로 나누기
* 각 조각마다 어떤 우선 순위로 선택을 내려야 할지 결정 후 작은 입력을 손으로 풀기
* 다음 두 속성이 적용되는지 확인   
   
* 탐욕적 선택 속성: 항상 각 단계에서 우리가 선택한 답을 포함하는 최적 해가 존재하나?
* 최적 부분 구조: 각 단계에서 항상 최적의 선택만을 했을 때, 전체 최적 해를 구할 수 있나?   

## 정렬 알고리즘 (Sorting Algorithm)
정렬 알고리즘은 크게 Comparisons 방식과 Non-Comparisons 방식으로 나뉜다.

### Comparisons Sorting Algorithm (비교 방식 알고리즘)
* Bubble Sort
* Selection Sort
* Insertion Sort
* Merge Sort
* Heap Sort
* Quick Sort   

#### Bubble Sort
N개의 원소를 가진 배열을 정렬할 때, In-place sort로 인접한 두 개의 데이터를 비교해가면서 정렬하는 방식이다. 가장 큰 값을 배열의 맨 마지막으로 이동시키면서 정렬하고자 하는 원소의 개수만큼 두 번 반복하게 된다.   
   
공간 복잡도: O(1)   
시간 복잡도: O(N^2)   

#### Selection Sort
N개의 원소를 가진 배열을 정렬할 때, 계속 바꾸는 것이 아닌 비교하고 있는 값의 Index를 저장해둔다. 최종적으로 한 번만 바꿔준다. 하지만 여러 번 비교 하는 것은 같다.   
   
공간 복잡도: O(1)   
시간 복잡도: O(N^2)   

#### Insertion Sort
N개의 원소를 가진 배열을 정렬할 때, I번째를 정렬할 순서라고 가정한다면 0부터 I-1까지의 원소들은 정렬되어 있다는 가정하에 I번째 원소와 I-1번째 원소부터 0번째 원소까지 비교하면서 I번째 원소가 비교하는 원소보다 클 경우에 서로의 위치를 바꾸고, 작을 경우에 위치를 바꾸지 않고 다음 순서의 원소와 비교하면서 정렬한다. 이 과정을 정렬하려는 배열의 마지막 원소까지 반복한다.   
   
공간 복잡도: O(1)   
시간 복잡도: O(N^2)   

#### Merge Sort
N개의 원소를 가진 배열을 정렬할 때, 정렬하고자 하는 배열의 크기를 작은 단위로 나눠 정렬하고자 하는 배열의 크기를 줄이는 원리이다. ```Divide and Conquer``` "분할하여 정복한다"의 원리이다. 복잡한 문제를 복잡하지 않은 문제로 분할하여 정복하는 방법이다. 단, 분할해서 정복했으니 정복한 후에는 <b>결합(Combine)</b>의 과정이 거쳐야 한다.   

Merge Sort는 더이상 나누어지지 않을 때까지 반으로 분할하다가 더 이상 나누어지지 않은 경우(원소가 하나인 배열)에는 자기 자신, 원소 하나를 반환한다. 원소가 하나인 경우에 정렬할 필요가 없다. 이 때, 반환한 값끼리 결합될 때, 비교가 이루어지며, 비교 결과를 기반으로 정렬되어 <b>임시 배열에 저장</b>된다. 그리고 임시 배열에 저장된 순서를 합쳐진 값을 반환한다. 실제 정렬은 나눈 것을 병합하는 과정에서 이루어진다.   

결국 하나씩 남을 때까지 분할하는 것이면 바로 하나씩 분할할 수 있을까? 재귀적으로 정렬하는 원리이다. 재귀적 구현을 위하 반씩 분할한다.   
   
공간 복잡도: O(N)   
시간 복잡도: O(NlogN)   

#### Heap Sort
```Binary Heap``` 자료구조를 활용할 정렬 방법에는 두 가지 방법이 있다. 정렬의 대상인 데이터들을 힙에 넣었다가 꺼내는 원리로 정렬하게 되는 방법과 기존의 배열을 ```Heapify``` (Heap으로 만들어주는 과정)을 거쳐 꺼내는 원리로 정렬하는 방법이다. Heap에 데이터를 저장하는 시간 복잡도는 ```O(log N)```이며, 삭제 시간 복잡도도 동일하다. 힙 자료구조를 사용하여 정렬하는데 Time Complexity는 ```O(log N)```이 된다. 정렬하려는 대상이 n개라면 Time Complexity는 ```O(NlogN)```이 된다.   
   
공간 복잡도: O(1)   
시간 복잡도: O(NlogN)   

#### Quick Sort
정렬 기법 중 가장 빠르다는 이유로 Quick이라는 단어가 붙었다. 그러나 Worst Case에서 시간복잡도가 O(N^2)가 나올 수 있다. 그러나 ```Constant factor```가 작아서 속도가 빠르다.   

Quick Sort는 Divide and Conquer 전략을 사용하여 정렬한다. Divide 과정에서 <b>Pivot</b> 개념이 사용된다. 배열을 오름차순으로 정렬한다면 Pivot을 기준으로 좌측은 Pivot보다 작은 값이 위치하고, 우측은 큰 값이 위치하도록 Partition된다. 이렇게 나누어진 좌, 우측의 각각 배열을 다시 재귀적으로 Quick Sort를 시키면 다시 Partition 과정이 적용된다. 이 때, 주의할 것은 Partition 과정에서 Pivot으로 설정된 값은 다음 재귀 과정에서 포함하지 않아야 된다. 이미 Partition 과정에서 정렬된 자신의 위치를 찾아기 때문이다.   

* Quick Sort's Worst Case   
Quick Sort로 오름차순 정렬할 때, Partition 과정에서 Pivot의 값이 항상 배열 내 가장 작은 값 혹은 큰 값으로 설정되었을 때다. 매 Partition마다 ```Unbalanced Partition```이 이루어지고 이렇게 Partition이 되면 비교 횟수는 원소 N개에 대해 N번, (N-1)번, (N-2)번 등이 되므로 시간복잡도는 O(N^2)가 된다.   
   
* Balanced Partition   
Best-Case는 두 개의 Sub-problems의 크기가 동일한 경우가 된다. 즉, Partition 과정에서 반반씩 나누어지게 되는 경우인 것이다. 그래서 Partition 과정에서 pivot을 어떻게 정할 것인가가 중요해진다. Balanced Partition (균형 분할)을 할 수 있기 위해 특정 위치의 원소를 pivot 으로 설정하지 않고 배열 내의 원소 중 임의의 원소를 pivot으로 설정하면 입력에 관계없이 일정한 수준의 성능을 얻을 수 있다. 또한 악의적인 입력에 대해 성능 저하를 막을 수 있다.   

* Partitioning   
가장 마지막 원소를 pivot 으로 설정했을 때, pivot의 값을 기준으로 좌측에는 작은 값 우측에는 큰 값이 오도록 해야 하는데, pivot은 움직이지 않도록 가정한다. 첫번째 원소부터 비교하는데 만약 그 값이 pivot보다 작다면 그대로 두고 크다면 맨 마지막에서 그 앞의 원소와 자리를 바꿔준다. 즉, Pivot의 값의 Index가 <b>K</b>라면 <b>K-1번째</b>와 바꿔주는 것이다. 이 모든 원소에 대해 실행하고 마지막 과정에서 작은 값들이 채워지는 인덱스를 가리키고 있는 값에 <b>1</b>을 더한 Index 값과 Pivot 값을 바꿔준다. 즉, 최종적으로 결정될 Pivot의 인덱스를 <b>I</b>라고 했을 때, 0부터 I-1까지는 Pivot보다 작은 값이 될 것이고 I+1 부터 K까지는 Pivot 값보다 큰 값이 될 것이다.   
   
공간 복잡도: O(log(N))   
시간 복잡도: O(NlogN)   

## Non-Comparisons Sorting Algorithm
Counting Sort, Radix Sort를 확인한다.

### Counting Sort
Count Sort는 말 그대로 몇 개인지 개수를 세어 정렬하는 방식이다. 정렬하고자 하는 값 중 최대 값에 해당하는 값을 Size로 하는 임시 배열을 만든다. 만들어진 배열의 Index 중 일부는 정렬하고자 하는 값들이 되므로 그 값에는 그 값들의 개수 를 나타낸다. 정렬하고자 하는 값들이 몇 개씩인지 파악하는 임시 배열이 만들어졌다면 이 임시 배열을 기준으로 정렬을 한다. 그 전에 임시 배열에서 한 가지 작업을 추가적으로 수행해주어야 하는데, 큰 값부터 즉, 큰 Index부터 시작하여 누적된 값으로 변경해주는 것이다. 이 누적된 값은 정렬하고자 하는 값들이 정렬될 Index 값을 나타내게 된다. 작업을 마친 임시 배열의 Index는 정렬하고자 하는 값을 나타내고 Value는 정렬하고자 하는 값들이 정렬되었을 때의 Index를 나타내게 된다. 이를 기준으로 정렬을 해준다. 점수와 같이 0~100 으로 구성되는 좁은 범위에 존재하는 데이터들을 정렬할 때 유용하게 사용할 수 있다.   
   
공간 복잡도: O(N)   
시간 복잡도: O(N)   

### Radix Sort
정렬 알고리즘의 한계는 O(NlogN)이지만, 기수 정렬은 이 한계를 넘어설 수 있는 알고리즘이다. 단, 한 가지 단점이 존재하는데 적용할 수 있는 범위가 제한적이라는 것이다. 이 범위는 데이터 길이에 의존하게 된다. 정렬하고자 하는 데이터의 길이가 동일하지 않은 데이터에 대해서는 정렬이 불가능하다. 숫자가 아닌 문자열의 경우도 마찬가지이다. (불가능하다는 것은 기존의 정렬 알고리즘에 비해 기수 정렬 알고리즘으로는 좋은 성능을 내는데 불가능하다는 것이다.)   

기수(radix)란 주어진 데이터를 구성하는 기본 요소를 의미한다. 이 기수를 이용해서 정렬을 진행한다. 하나의 기수마다 하나의 버킷을 생성하여, 분류를 한 뒤에, 버킷 안에서 또 정렬을 하는 방식이다.   

기수 정렬은 LSD(Least Significant Digit) 방식과 MSD(Most Significant Digit) 방식 두 가지로 나뉜다. LSD는 덜 중요한 숫자부터 정렬하는 방식으로 예를 들어 숫자를 정렬한다고 했을 때, 일의 자리부터 정렬하는 방식이다. MSD는 중요한 숫자부터 정렬하는 방식으로 세 자리 숫자면 백의 자리부터 정렬하는 방식이다.   

두 가지 방식의 Big-O는 동일하다. 하지만 주로 기수정렬을 이야기할 때는 LSD를 이야기한다. LSD는 중간에 정렬 결과를 볼 수 없다. 무조건 일의 자리부터 시작해서 백의 자리까지 모두 정렬이 끝나야 결과를 확인할 수 있고, 그 때서야 결과가 나온다. 하지만 MSD는 정렬 중간에 정렬이 될 수 있다. 그러므로 정렬하는데 걸리는 시간을 줄일 수 있다. 하지만 정렬이 완료됬는지 확인하는 과정이 필요하고 이 때문에 메모리를 더 사용하게 된다. 또 상황마다 일관적인 정렬 알고리즘을 사용하여 정렬하는데 적용할 수 없으므로 불편하다. 이러한 이유들로 기수 정렬을 논할 때는 주로 LSD에 대해서 논한다.   
   
공간 복잡도: O(N)   
시간 복잡도: O(N)   

### 정렬 알고리즘 정리
|Algorithm|Space Complexity|(average) Time Complexity|(worst) Time Complexity|
|:---:|:---:|:---:|:---:|
|Bubble sort|O(1)|O(N^2)|O(N^2)|
|Selection sort|O(1)|O(N^2)|O(N^2)|
|Insertion sort|O(1)|O(N^2)|O(N^2)|
|Merge sort|O(N)|O(NlogN)|O(NlogN)|
|Heap sort|O(1)|O(NlogN)|O(NlogN)|
|Quick sort|O(1)|O(NlogN)|O(N^2)|
|Count sort|O(N)|O(N)|O(N)|
|Radix sort|O(N)|O(N)|O(N)|   

## Prime Number Algorithm
소수란 양의 약수를 딱 두 개만 갖는 자연수를 소수라 부른다. 2, 3, 5, 7, 11 등을 말하며, 소수를 판별하는 방법으로 첫번째 어떤 수 N이 소수인지 판별하기 위해서는 N을 2부터 N보다 1 작은 수까지 나누어서 나머지가 0인 경우가 있는지 검사하는 방법과 두번째로 ```에라토스테네스의 체```를 사용할 수 있다.   

### 에라토스테네스의 체 (Eratosthenes’ sieve)
```에라토스테네스의 체(Eratosthenes’ sieve)```는 임의의 자연수에 대하여, 해당 자연수 이하의 소수(prime number)를 모두 찾아 주는 방법이다. 에라토스테네스의 체를 사용하면 특정 자연수 이하의 합성수는 다 지워지고 소수들만 남는다. 방법은 간단하다. 만일 100 이하의 소수를 모두 찾고 싶다면, <b>1</b>부터 <b>100</b>까지의 자연수를 모두 나열한 후, 먼저 소수도 합성수도 아닌 1을 지우고, 2 이외의 2의 배수들을 다 지우고, 3외의 3의 배수들을 다 지우고, 5외의 5의 배수들을 지우는 등의 이 과정을 100제곱근인 10이하의 소수들에 대해서만 반복하면, 이 때 남은 수들이 구하고자 하는 소수들이다.   

예를 들어서 50까지의 소수를 구하는 것은   
1. 초기 상태   
<br>
|1|2|3|4|5|6|7|8|9|10|
|11|12|13|14|15|16|17|18|19|20|
|21|22|23|24|25|26|27|28|29|30|
|31|32|33|34|35|36|37|38|39|40|
|41|42|43|44|45|46|47|48|49|50|   

2. 소수도 합성수도 아닌 1 제거   
|X|2|3|4|5|6|7|8|9|10|
|11|12|13|14|15|16|17|18|19|20|
|21|22|23|24|25|26|27|28|29|30|
|31|32|33|34|35|36|37|38|39|40|
|41|42|43|44|45|46|47|48|49|50|   

3. 2 외의 2 의 배수들을 제거   
|X|2|3|X|5|X|7|X|9|X|
|11|X|13|X|15|X|17|X|19|X|
|21|X|23|X|25|X|27|X|29|X|
|31|X|33|X|35|X|37|X|39|X|
|41|X|43|X|45|X|47|X|49|X|   

4. 3 외의 3 의 배수들을 제거   
|X|2|3|X|5|X|7|X|X|X|
|11|X|13|X|X|X|17|X|19|X|
|X|X|23|X|25|X|X|X|29|X|
|31|X|X|X|35|X|37|X|X|X|
|41|X|43|X|X|X|47|X|49|X|   

5. 5 외의 5 의 배수들을 제거   
|X|2|3|X|5|X|7|X|X|X|
|11|X|13|X|X|X|17|X|19|X|
|X|X|23|X|X|X|X|X|29|X|
|31|X|X|X|X|X|37|X|X|X|
|41|X|43|X|X|X|47|X|49|X|   

6. 7 외의 7 의 배수들을 제거 (50 이하의 소수 판별 완료)   
|X|2|3|X|5|X|7|X|X|X|
|11|X|13|X|X|X|17|X|19|X|
|X|X|23|X|X|X|X|X|29|X|
|31|X|X|X|X|X|37|X|X|X|
|41|X|43|X|X|X|47|X|X|X|   

공간복잡도: O(N)   
시간복잡도: O(loglogN)   

## Time Complexity
* O(1) < O(logN) < O(N) < O(NlogN) < O(N^2) < O(N^3)
* O(2^N) : 크기가 N 인 집합의 부분 집합
* O(N!) : 크기가 N 인 순열

[알고리즘 출처](https://github.com/JaeYeopHan/Interview_Question_for_Beginner/tree/master/Algorithm#dp%EB%8F%99%EC%A0%81-%EA%B3%84%ED%9A%8D%EB%B2%95)