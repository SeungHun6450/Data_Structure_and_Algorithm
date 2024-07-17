# 배열(Array)

- 같은 타입의 데이터들을 저장하는 자료 구조
- **연속된 메모리 공간**에 데이터들을 저장
  - 같은 타입의 데이터들은 **연속된 메모리 공간**을 사용하며 이곳에 데이터들을 할당 받는다
    ex) Example_Array = [4, 2, 5, 8, 4, 11, 15]

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/c443d179-2422-4eef-a00d-14579bacdc83/58046598-c759-450f-8746-24946d52160a/Untitled.png)

- 데이터들 각각의 이름은 없지만 인덱스로 접근 가능
  ex) Example_Array [0] ⇒ 4
  Example_Array [3] ⇒ 8
- 인덱스는 offset 개념으로 사용된다
  - **offset** : 동일 오브젝트 안에서 오브젝트 처음부터 주어진 요소나 지점까지의 변위차를 나타내는 정수형이다
- 연속된 메모리 공간에 데이터들을 저장하기 때문에, [**CPU Cache**](https://www.notion.so/9afe4bb138044c9d827d1fefd723d0b6?pvs=21)를 통해 같은 배열에 있는 다른 데이터에 접근하는 시간을 단축할 수 있다
- 배열은 데이터를 읽을 때는 빠르다, 이유는 RAM에 저장되어있는 공간에 랜덤으로 접속이 가능해서
  - RAM(Random Access Memory) : 휘발성 메모리, 컴퓨터를 끄고 켰을 때 초기화가 된다
    - 프로그램이 실행되고, 변수를 생성할 때, 모두 RAM에 저장된다
    - 하드 드라이브보다 RAM이 읽는 속도가 빠르다, 이유는 데이터 접속이 랜덤 하기 때문이다. 이것을 설명하면 아래와 같다
      - RAM을 마을이라 생각하면 마을 안에 단지들에 데이터를 보관할 수 있다
      - 이 단지들을 Memory Address라고 한다
      - 이 단지에 접근을 할 때, 원하는 단지에 가기 위해 0단지 부터 순서대로 가는 것이 아닌 원하는 곳을 바로 찾아서 간다
- 하지만 검색, 추가, 삭제해야 할 때 느려지며, 배열의 맨 끝에서 작업을 하는 것이 가장 빠르다. 이는 선형 검색(Linear Search)을 하기 때문이다
- 처음 혹은 중간에 추가 및 삭제를 하는 경우 배열 안의 값들을 앞쪽으로 당기고, 뒤에서 당기는 작업을 해야 하기 때문에 느려진다

### ❓2차원 배열은 어떻게 저장될까?

- 시각화를 하게 되면, 아래의 그림과 같이 메모리에 순차적으로 저장이 된다
- 2차원처럼 보이지만, 실제로는 1차원으로 표현이 된다
  ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/c443d179-2422-4eef-a00d-14579bacdc83/3c7b195b-b95c-414f-861f-9de70c69bd1f/Untitled.png)

### ❓객체를 메모리에 담게 되면 어떻게 저장될까?

- 해당 배열에는 객체의 reference(참조)를 저장을 한다
  - **reference(참조) :** 프로그램이 메모리나 다른 저장 공간에서 특정 변수의 값이나 레코드에 접근할 수 있도록 하는 값이다
    메모리 상의 객체의 주소 또는 참조 값이 그 예시이다.
- 각 객체들은 메모리 상에 존재하며, 각 객체의 메모리 주소 혹은 reference를 배열 저장한다
- 아래의 그림을 보면 0, 1, 2 각 인덱스가 저장된 값들은, 각각의 reference를 저장한다
- 객체들을 배열에 저장할 때, **연속된 메모리 공간에 저장** ⇒ 객체들의 reference들이 저장된다는 의미이다
- 실제로 각각의 객체들은 연속된 공간이 아닌 아래의 그림처럼 띄엄 띄엄 저장 된다

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/c443d179-2422-4eef-a00d-14579bacdc83/1dfa1159-3400-4d45-b726-01a4cdef35f2/Untitled.png)

## 1. Dynamic array(동적 배열)

- 크기가 변할 수 있는 array
- 데이터를 더하거나 빼는 것이 가능한 자료 구조
- resizable array, array list 등등으로 불린다
- 런타임중에 메모리가 할당되며, 메모리는 [힙](https://www.notion.so/9afe4bb138044c9d827d1fefd723d0b6?pvs=21)에 할당된다
  - 런타임 : 컴파일 과정을 마친 컴퓨터 프로그램이 실행되고 있는 환경 또는 동작되는 동안의 시간을 말한다
    - javascript가 Web Browser에서 실행된다면 런타임 환경은 Web Browser
- 메모리 할당을 해제하고 원하는 경우 베열의 크기를 변경할 수 있다

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/c443d179-2422-4eef-a00d-14579bacdc83/5357bd26-f8c0-4dd3-b055-abb0724399a8/Untitled.png)

## 2. Associative array(연관 배열)

- key-value 쌍을 저장하는 ADT
  - ADT : 구현하고자 하는 구조에 대해 구현 방법은 명시하지 않는 것
- 같은 key를 가지는 쌍은 최대 한 개만 존재
- map, dictionary라고 불리기도 함
- 배열의 크기를 변경하거나 업데이트 할 수 없다, 즉 크기가 고정된다
- 컴파일 타임 동안 메모리가 할당되며, 메모리는 [스택](https://www.notion.so/9afe4bb138044c9d827d1fefd723d0b6?pvs=21)에 할당된다
  - 컴파일 : 개발자가 프로그램을 위해 작성한 소스코드를 다른 프로그램이나 기계(H/W)가 처리하기 용이한 형태로 바꾸는 과정
    - 사람이 이해하는 언어로 작성한 코드를 컴퓨터가 이해할 수 있는 언어로 바꿔주는 과정
    - java, c, c++은 컴파일 언어이므로 런타임이 되기 위해 반드시 컴파일 과정을 거쳐야함
    - javascript, php, python은 스크립트 언어이며 이 언어들은 컴파일 과정 없이 기계어로 번역되어 즉시 동작하도록 되어있다
      따라서 컴파일 과정은 필요하지 않지만 작동 시 컴파일 언어에 비해 느리다

| 사원 이름 | id  |
| --------- | --- |
| 사원1     | 1   |
| 사원2     | 2   |

## **코드 구현**

1. 문자열 뒤집기

```jsx
function reverse(str) {
  const reverseString = str.split("");
  let result = "";
  for (let i = reverseString.length; i > 0; i--) {
    result += reverseString[i - 1];
  }
  console.log(result);
  return result;
}
```

1. 문자열 분할

```jsx
function split(str, del) {
  let result = "";
  let result_array = [];
  str = str + del;
  for (let i = 0; i < str.length; i++) {
    if (str[i] !== del) {
      result += str[i];
    } else {
      if (result.length !== 0) {
        result_array.push(result);
        result = "";
      }
    }
  }
  return result_array.forEach((result_each) => {
    document.write(result_each + "<br>");
  });
}
```

1. 문자열 결합

```jsx
let myName = ["FirstName", "LastName"];

function join(str, sep) {
  str = str || [];
  sep = sep || " ";
  let result = "";
  for (let i = 0; i < str.length; i++) {
    if (i === 0) {
      result += str[i];
    } else if (i > 0) {
      result += sep + str[i];
    }
  }
  console.log(result);
  return result;
}
```

1. 문자열 부분 검색

```jsx
function partSearch(str, search) {
	let count = 0;
	for(let i = 0; i <= str.length - search.length ; i++ {
		let isFound = true;
		for(let j = 0; j < search.length ; j++) {
			if(str[i+j] !== search[j]) {
			  !isFound
				break;
			}
		}
		if(isFound){
			count ++;
		}
	}
	return count;
}
```

1. 문자열 회문 검사

```jsx
function palindrome(str) {
  for (let i = 0; i < str.length / 2; i++) {
    if (str[i] !== str[str.length - i - 1]) {
      return false;
    }
  }
  return true;
}
```

## **번외 : CPU와 스택&힙**

### 1. CPU Cache란?

1. CPU Cache : CPU가 자주 사용할만한 데이터를 메인 메모리에서 꺼내와 복사, 저장해 놓는 임시 저장소이다

- CPU 내부나 바로 옆에 존재하는 작은 메모리칩(하드웨어)이다

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/c443d179-2422-4eef-a00d-14579bacdc83/d2341f22-437c-478c-b0f2-0e216d592ad3/Untitled.png)

- CPU 의 성능이 발달하면서 CPU코어와 메인 메모리간의 속도 차이가 현저히 증가하여, 이 둘 사이의 데이터 접근 시간을 줄이기 위해 캐시 메모리 개념을 도입했다

1. CPU 캐시 메모리의 종류

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/c443d179-2422-4eef-a00d-14579bacdc83/edaf2330-e354-421c-bdd4-0d081c840985/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/c443d179-2422-4eef-a00d-14579bacdc83/4faa2f57-702c-467d-9a77-bb57bdfa26c6/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/c443d179-2422-4eef-a00d-14579bacdc83/5b5dede4-425a-454e-b948-57651d148cda/Untitled.png)

- CPU Cache Memory는 캐시의 크기와 속도를 기준으로 L1, L2, L3로 나뉜다
  - L1 cahce
    - CPU core 칩 내부에 존재
    - CPU가 매우 빠르게 접근 가능, 크기가 작다
    - 렘 기준 최대 100배의 속도
    - L1 cahce는 두 가지로 나뉜다
    1. 명령캐시 : cpu가 사용할 데이터가 저장
    2. 데이터 캐시 : 메인 메모리에 기록될 데이터가 저장
  - L2 cache
    - CPU core 칩 내, 외부 둘 다 존재할 수 있다
    - 렘 기준 최대 25배의 속도
    - L1 캐시에 찾고자 하는 데이터가 없을 경우(cache miss) 사용된다
    - L1보다 느리고 크기가 더 크다
  - L3 cache
    - L1, L2보다 크고 속도가 느리다
    - 렘보다 빠르다
    - 멀티코어 환경에서 각각의 코어는 독립적인 L1, L2 메모리를 소유함과 동시에 L3를 공유한다

1. CPU 캐시 동작 과정
   1. CPU가 메모리에 데이터를 요청
   2. CPU가 메인 메모리에 접근하기 전, 필요로 하는 데이터가 캐시에 존재하는지 확인(check)
   3. 있으면(chche hit) 캐시에 접근하여 데이터를 가져옴
   4. 없으면(chche miss) 메인 메모리에 접근해서 데이터를 가져옴

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/c443d179-2422-4eef-a00d-14579bacdc83/f0516eb8-8f61-444e-bda1-ae1ae16fc3da/Untitled.png)

### 2. stack & heap ⇒ 메모리 구조?

- 메모리 구조 : 프로그램이 실행되기 위해 프로그램이 메모리에 로드되어야 하며, 사용되는 변수들을 저장할 메모리가 필요하다
  따라서 컴퓨터의 운영체재는 프로그램의 실행을 위해 다양한 메모리 공간을 제공하는데 , 대표적인 메모리 공간은 다음과 같이 4가지가 있다.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/c443d179-2422-4eef-a00d-14579bacdc83/e3f9a092-5872-4a33-be88-07421f233f59/Untitled.png)

- 코드 영역 : 실행할 프로그램의 코드가 저장되는 영역으로 텍스트(code) 영역이라고도 부른다
  CPU는 코드 영역에 저장된 명령어를 하나씩 가져가서 처리하게 된다
- 데이터 영역 : 프로그램의 전역 변수와 정적(static) 변수가 저장되는 영역이다
  데이터 영역은 프로그램의 시작과 함께 할당되며, 프로그램이 종료되면 소멸한다
- 스택 영역 : 함수의 호출과 관계되는 지역 변수와 매개변수가 저장되는 영역
  - 스택 영역은 함수의 호출과 함께 할당되며, 함수의 호출이 완료되면 소멸
  - 이렇게 스택 영역에 저장되는 함수의 호출 정보를 스택 프레임(stack frame)이라고 한다
  - 스택 영역은 푸시(push) 동작으로 데이터를 저장하고, 팝(pop) 동작으로 데이터를 인출한다
  - 이러한 스택은 후입선출(LIFO, Last-In First-Out) 방식에 따라 동작하므로, 가장 늦게 저장된 데이터가 가장 먼저 인출되며, 스택 영역은 메모리의 높은 주소에서 낮은 주소의 방향으로 할당된다
  - **변수의 크기를 조정할 수 없다**
- 힙 영역 : 사용자가 직접 관리할 수 있는 ‘그리고 해야만 하는’ 메모리 영역이다
  - 힙 영역은 **사용자에 의해 메모리 공간이 동적으로 할당되고 해제**된다
  - 힙 영역은 메모리의 낮은 주소에서 높은 주소의 방향으로 할당된다
