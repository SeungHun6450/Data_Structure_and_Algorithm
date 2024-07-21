# 리스트

## **1. ADT 관점 에서의 List**

- 값(value)들을 저장하는 추상자료형(ADT)
- 순서가 있음
- 중복을 허용
- Set이나 Map을 사용 하는 것이 더 적절한 상황이 아닐 때
  - 사용처 : 객관식 문제의 정답, 00의 순위

## **2. List 구현체**

- Array List : **배열을 사용**하여 구현
- Linked List : **노드를 연결**시키는 형태로 구현

### 2-1. 단일 연결 리스트

![image](https://github.com/user-attachments/assets/6ab22872-9670-4ef8-9fae-26f5ff38ab27)


- data 에는 값, next에는 pointer나 reference를 저장하고 있다
- next는 다음 노드를 가리키는 pointer나 reference를 가지고 있다
- 처음을 head, 마지막은 tail이라 한다
- Array List와 달리 메모리 공간에서 띄엄 띄엄 저장이 된다 (이는 pointer나 reference를 가지고 있으므로 유추가 가능하다)
- 배열의 head와 tail은 추가한 순서나 메서드에 따라 달라진다

### 2-2. 이중 연결 리스트

![image](https://github.com/user-attachments/assets/3d459837-2c98-4f1e-9759-7c4457a92914)


- 양방향 통행
- 양방향 이므로 어떤 방향이든 빨리 접근할 수 있다

### 2-3. 원형 연결 리스트

![image](https://github.com/user-attachments/assets/30da5e13-a8ec-41dc-bfb5-3db366f75bec)


- tail이 가리키고 있는 마지막 노드가 가장 앞에 있는 head를 가리키는 구조
- 이때, head는 따로 관리하지 않고 tail만 관리한다(head가 없어도 관리가 가능하기 때문)
- 단일 또는 이중으로 연결될 수 있다

### 2-4. 이중 원형 연결 리스트

![image](https://github.com/user-attachments/assets/0ce01cf8-7f80-44b9-ab8e-201283d9d90e)

- 이중 + 원형 연결 리스트
- head와 tail이 서로 연결 + 노드들이 앞뒤로 연결되어 있는 구조

## Array List VS Linked List

![image](https://github.com/user-attachments/assets/844a6e15-cea1-4b90-8185-36e7d298fb82)


Java는 Array List를 쓰는 추세(?)이다
