## 1. 스택(Stack)

먼저 넣은 게 나중에 나오고, 나중에 넣은 게 먼저 나오는 구조

배열이나 리스트로 구현하는데 배열로 구현하는 것이 좋다

- LIFO : Last in First Out
- FILO : First in Last Out

상자 안에 책을 차례로 넣고 꺼내는 것을 생각하면 된다

브라우저에서 뒤로 가기 기능, 되돌리기 Ctrl + z

- push : 스택에 넣을 때
- pop : 스택에서 뺄 때

javascript에서 push()메소드와 pop()메소드를 생각하면 이해하기 쉽다!

```jsx
const stack = [];

let index = 0;
const push = (val) => {
  stack[index] = val;
  index++;
};

const pop = () => {
  if (index === 0) return null;
  const result = stack[--index];
  return result;
};

push(1); // stack.push(1); [1]
push(2); // stack.push(2); [2]
pop(); // stack.pop(); 2
pop(); // stack.pop(); 1
```

## 2. 큐(Queue)

먼저 넣은 것을 먼저 빼고 나중에 넣은 것을 나중에 뺀다

- LILO : Last in Last Out
- FIFO : First in First Out

**순서를 보장한다**

은행의 번호표를 뽑고 발급 순서대로 카운터에서 호출하는 것과 같다

이메일 전송, 쇼핑몰 주문

- enqueue(push) : 데이터 삽입
- dequeue(shift) : 데이터 삭제

```jsx
const queue = [];
let first = 0;
let last = 0;

const enqueue = (val) => {
	queue[last++] = val
};

const dequeue = () => {
	if(first>=last) return null;
	const result = queue[first++];
	return result;
};

enqueue(1); // queue : [1] first: 0 last: 1
enqueue(2); // queue : [1, 2] first: 0 last: 2
dequeue()); // 1 , first: 1 last: 2
dequeue()); // 2 , // first: 2 last: 2
```

## 3. 덱**(Deque, Double-ended Queue)**

스택과 큐를 합친 자료구조여서 양 끝에서 데이터를 넣거나 추출할 수 있다

```jsx
const dequeue = [];
let first = 0;
let last = 0;

const push_first = (val) => {
  if (dequeue[0]) {
    for (let i = dequeue.length; i > 0; i--) {
      dequeue[i] = dequeue[i - 1];
    }
  }
  dequeue[first] = val;
  last++;
};
const push_last = (val) => {
  dequeue[last++] = val;
};
const pop_first = () => {
  if (first >= last) {
    return null;
  }
  const result = dequeue[first++];
  return result;
};
const pop_last = () => {
  if (first >= last) {
    return null;
  }
  const result = dequeue[--last];
  return result;
};
```
