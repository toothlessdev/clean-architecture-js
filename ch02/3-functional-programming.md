# 3. 함수형 프로그래밍 Functional Programming

> 할당문에 대해 규칙을 부과한다

## 1. 함수형 프로그래밍

```java
// Java
public class Mathematics {
    public static void main(String args[]) {
        for(int i = 0 ; i < 10 ; i++) {
            System.out.println(i * i);
        }
    }
}
```

```js
// JavaScript
const arr = new Array(10)
    .fill()
    .map((_, i) => i + 1)
    .map((i) => i * i);

console.log(arr);
```

| Java                   | JavaScript               |
| ---------------------- | ------------------------ |
| 가변변수 (`i`) 를 사용 | 가변변수를 사용하지 않음 |

## 2. 불변성과 아키텍쳐

### 1. 동시성문제와 가변변수

-   Race Condition, Deadlock, Concurrent Update 와 같은 문제는 모두 `가변변수` 에 의해 발생함

### 2. 가변성의 분리

#### 1. 가변 컴포넌트와 불변 컴포넌트

| 가변 컴포넌트 | 불변 컴포넌트                                                                                                                  |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| -             | 순수하게 함수형 방식으로만 작업이 처리 됨 <br/> `가변변수가 존재하지 않음` <br/> 불변 컴포넌트는 가변 컴포넌트와 서로 통신한다 |

2. 애플리케이션을 제대로 구조화하려면, 변수를 변경하는 컴포넌트와 변경하지 않는 컴포넌트를 분리 해야함 (Concurrency, Lock 때문)

### 2. Event Sourcing

-   상태가 아닌 트랜잭션 자체를 저장하는 전략
-   상태가 필요해지면, 상태의 시작점부터 모든 트랜잭션을 처리함
-   이를 통해 가변변수를 완전히 제거하여 완전한 불변성을 갖도록 만들 수 있고, 완전한 함수형 프로그래밍이 가능함
