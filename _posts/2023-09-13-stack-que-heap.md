---
title: Stack, Que, Heap와 자바스크립트 Event Loop
author: threeh
date: 2023-09-13 13:15:00 +0800
categories: [Data Structure]
tags: [Data Structure, Stack, Que, Heap, Javascript, Event Loop]
pin: true
math: true
mermaid: true
---

### **들어가며**

> Stack, Queue, Heap에 대한 설명과 자바스크립트 Event Loop에서 각 개념이 어떤 의미를 가지는지에 대해 정리한 글입니다.

<br>

## **자료구조(Data Structure)**

![Data_Structure_Map](/assets/img/post/Data_Structure/stack_queue_heap/Data_Structure_Map.png)

<br>

- 컴퓨터에서 쓰이는 데이터를 효율적으로 저장, 관리, 조작하는데 사용되는 이론.

<br> <br>

## **Stack, Queue, Heap**

- 자료구조에서 선형, 비선형 구조에 속하는 개념
  - 선형 구조 <br> 
    i. 자료를 구성하는 원소들이 하나씩 일렬로 나열된 형태로, 각 요소는 바로 앞 또는 바로 뒤에 위치한 요소와 연결된다. <br>
    ii. ex. 배열(Array), 연결 리스트(Linked List), 스택(Stack), 큐(Queue).

  <br>

  - 비선형 구조 <br>
    i. 자료를 구성하는 원소들이 계층적 또는 네트워크 형태로 연결되어 있는 형태로, 각 요소가 하나 이상의 요소와 연결될 수 있다. <br>
    ii. ex. 트리(Tree), 그래프(Graph).

<br>

## **Stack**

![Stack](/assets/img/post/Data_Structure/stack_queue_heap/Stack.png)

<br>

### Stack의 정의

- 한 쪽 끝에서만 자료를 넣거나 뺄 수 있는 형태의 선형 자료구조

<br>

### Stack의 특징

- 가장 마지막에 추가된 데이터가 가장 먼저 제거된다. <br>
  LIFO(Last In First Out) 구조라고 한다.

- push : 스택에 자료를 집어 넣는 것 <br>
  pop : 스택에서 자료 제거하고 반환하는 것

- Stack은 쌓아놓은 접시와 유사하다. <br>
  접시는 밑에 부터 차곡 차곡 쌓아 올려 보관하고 가장 위에 올린 접시부터 차례대로 사용한다.

<br>

### 자바스크립트 Event Loop에서 Stack의 의미

- 자바스크립트에서의 스택은 함수 호출과 관련된 실행 컨테스트를 관리하는데 사용된다.

- 함수가 호출될 떄마다 실행 컨텍스트가 스택에 하나씩 쌓이고 함수의 실행이 끝나면 컨텍스트가 하나씩 제거된다.

- 이렇게 스택은 함수의 실행 흐름을 관리한다. <br>
  (참고로 호출된 순서의 역으로 함수가 실행된다).

<br>

## **Queue**

![Queue](/assets/img/post/Data_Structure/stack_queue_heap/Queue.png)

<br>

### Queue의 정의

- 데이터를 넣는 쪽과 빼는 쪽이 다른 형태의 선형 자료구조

<br>

### Queue의 특징

- 가장 먼저 추가된 데이터가 가장 먼저 제거된다(선입선출) <br>
  FIFO(First In First Out) 구조라고 한다. <br>
  선입선출

- Enqueue : 큐에 데이터를 추가하는 것. <br>
  Dequeue : 큐에 데이터를 제거하여 반환하는 것

- Queue는 버스 정류장 대기줄과 유사하다. <br>
  버스 대기줄에 먼저 선 사람이 가장 먼저 버스에 탈 수 있다.

<br>

### 자바스크립트 Event Loop에서 Queue의 의미

- JavaScript에서 Queue는 비동기 함수의 순서를 정리하는데 사용된다.

- Web API에서 전달 받은 비동기 함수들의 순서를 정리하고 정리된 순서에 따라 비동기 함수들은 Event Loop를 통해 Call Stack에 전달된다.

- 비동기 함수 정리 우선 순위는 다음과 같다. <br>
  Microtask Queue > Animation Frames > Task Queue <br>

- 각각의 Que에 할당되는 함수는 다음과 같다. <br>
  Microtask Queue - Promise. <br>
  Animation Frames - 애니메이션 처리 함수. <br>
  Task Queue - setTimeout.

<br>

## **Heap**

![Heap](/assets/img/post/Data_Structure/stack_queue_heap/Heap.png)

<br>

### Heap의 정의

- 데이터를 특정 순서대로 정렬하고 관리하는 비선형 자료구조.

- 완전 이진 트리의 일종으로 우선 순위 큐를 위하여 만들어진 자료구조.

- 힙은 완전 이진 트리라는 형태의 트리 구조로 이루어져 있다. <br>
  (이진 트리 : 각각의 노드가 최대 두 개의 자식 노드를 가지는 트리 구조)

<br>

### Heap의 종류

힙은 크게 최대 힙(Max Heap)과 최소 힙(Min Heap)으로 구분된다.

- 최대 힙(Max Heap)
  - 부모 노드의 키 값이 자식 노드의 키 값보다 크거나 같은 완전 이진 트리.
  - Key(부모 노드) >= Key(자식 노드).

<br>

- 최소 힙(Min Heap)
  - 부모 노드의 키 값이 자식 노드의 키 값보다 작거나 같은 완전 이진 트리.
  - Key(부모 노드) <= Key(자식 노드).

<br>

### Heap의 특징

- 우선 순위가 높은 데이터가 제거되고 반환하는 구조.

- 힙을 사용하면 최대값과 최소값 조회, 데이터의 삽입, 삭제 등을 빠르게 수행할 수 있다.

<br>

### 자바스크립트 Event Loop에서 Heap의 의미

- Heap에는 동적으로 생성된 객체 데이터의 주소값(참조값)이 할당되는 영역이다.

- 여기서 더 이상 필요하지 않은 객체들은 가비지 컬렉터에 의해 감지되고 제거된다.
  (가비지 컬렉터 : 메모리에 할당된 데이터를 해제하는 청소부).

<br>

## Event Loop
자바스크립트 코드는 입력된 순서에 따라 순차적으로 출력이 되는데 어떤 함수는 순서에 맞지 않게 출력되는 경우를 볼 수 있다 보통 이런 경우는 비동기 함수 떄문인데 Event Loop를 통해 자바스크립트 코드의 동작 과정에 대해 이해해보자.

![Event_Loop](/assets/img/post/Event_Loop/Event_Loop.png)

<br>

## Event Loop에 나오는 용어 설명

### Heap

- Heap에는 동적으로 생성된 객체 데이터의 주소값(참조값)이 할당되는 영역이다.

<br>

### Call Stack

- 실행될 코드가 한줄 단위로 할당되고 실행되는 영역

- LIFO(Last In First Out) 구조로 되어 있다. <br>
  가장 마지막에 추가된 데이터가 가장 먼저 나가는 방식 or 구조. <br>

- 참고로 Call Stack의 최대 사이즈는 12만개라고 한다(Chrome 기준). <br>
  (Call Stack의 최대 사이즈를 초과할 경우 브라우저가 종료된다고 한다).

<br>

### Web API

- 비동기 처리 함수를 관리하는 영역 <br>
  (브라우저에서는 Web API로 설명되고 Node에서는 백그라운드로 설명된다).

- 비동기 처리가 이루어진다(함수 내용이 출력되지는 않는다).

- Web API에 있는 함수는 Callback Queue로 전달된다.

- 비동기 처리로 넘어오는 비동기 함수로는 setTimeout, Promise, async & await 등이 있다. <br>

  (참고로 Promise는 동기 함수이다 - pending, 그러나 .then을 만나면 비동기 함수로 바뀐다).

<br>

### Callback Queue

- Web API에서 전달 받은 함수들을 관리하는 영역.

- Web API에서 전달 받은 비동기 함수들의 순서를 정리하고 정리된 순서에 따라 비동기 함수들은 Event Loop를 통해 Call Stack에 전달된다.

- Queue라는 자료 구조로 이루어져 있다.

- Callback Queue는 Microtask Queue, Animation Frames, Task Queue(Event Queue)로 이루어져 있다. <br>

  (Callback Queue를 Task Queue 또는 Event Queue라고 설명하기도 하는데 엄밀히 말하면 Callback Queue안에 Task Queue(Event Queue)가 있는 것이라고 한다).

  <br>

- 비동기 함수 정리 우선 순위는 다음과 같다. <br>
  Microtask Queue > Animation Frames > Task Queue <br>

- 각각의 Callback Que에 할당되는 함수는 다음과 같다. <br>
  Microtask Queue - Promise. <br>
  Animation Frames - 애니메이션 처리 함수. <br>
  Task Queue - setTimeout.

<br>

### Event Loop

- Callback Queue에 할당된 함수를 우선 순위에 맞춰 Call Stack에 할당해주는 영역 <br>
  이때, Call Stack이 비어있는지 확인하고 비어있을 경우 함수를 Call Stack에 할당해준다.

<br>

## Event Loop 동작 과정 예시

EX1

```
const foo = () => console.log("First");
const bar = () => setTimeout(() => console.log("Second"), 500);
const baz = () => console.log("Third");

bar();
foo();
baz();
```

위의 코드들은 어떤 순서로 동작할까. <br>
아래 그림을 통해 내부적으로 어떻게 동작하는지 확인해보자.

![Event_Loop](/assets/img/post/Event_Loop/Event_Loop_ex_01.gif)

https://dev.to/lydiahallie/javascript-visualized-event-loop-3dif

<br>

1. bar() 함수가 Call Stack에 할당된다. 이 함수는 비동기 함수이므로 Web API로 전달된다.

2. foo 함수가 Call Stack에 할당되고 함수의 내용인 First가 출력된다.

3. 0.5초 경과 후 bar 함수가 Microtask Queue로 전달된다(baz() 함수가 실행되어 Call Stack으로 전달되지 않는다).

   - 비동기로 넘어간 함수는 동기 함수가 Call Stack에서 전부 처리된 이후에 Event Loop를 통해 Call Stack으로 전달 된다.

   <br>

4. baz() 함수가 Call Stack에 할당되고 함수의 내용인 Third가 실행된다.

5. Callback Queue에 있던 foo() 함수가 Event Loop를 통해 Call Stack으로 전달된다.

6. foo 함수가 실행되고 Second가 실행된다.

- First, Third, Second 순으로 출력된다.

<br>

### EX2

```
const func1 = () => setTimeout(() => console.log("First Running"), 100);
const func2 = () => console.log("1");
const func3 = () => console.log("2");
const func4 = () => console.log("3");
const func5 = () => console.log("4");
const func6 = () => console.log("5");
const func7 = () => console.log("6");
const func8 = () => console.log("7");
const func9 = () => console.log("8");
const func10 = () => console.log("9");
const func11 = () => console.log("10");

func1();
func2();
func3();
func4();
func5();
func6();
func7();
func8();
func9();
func10();
func11();
```

위 코드를 실행해보면 1~10까지 순차적으로 출력되고 마지막에 First Runnung이 출력된다.

비동기로 넘어간 함수는 동기 함수가 Call Stack에서 전부 처리된 이후에 Event Loop를 통해 Call Stack으로 전달 되기 때문이다.

<br>


## **참고 자료**
- Stack, Que, Heap
  - Wikipedia
  - https://www.geeksforgeeks.org/heap-data-structure/

- Event Loop
  - https://alok-verma6597.medium.com/event-loop-in-javascript-431003755cd4

  - https://dev.to/lydiahallie/javascript-visualized-event-loop-3dif

  - https://youtu.be/8aGhZQkoFbQ?si=45bF079d2yoHaWbX
