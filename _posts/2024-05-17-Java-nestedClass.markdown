---
layout: post
title:  "Java: Nested Class"
date:   2024-05-17 09:00:00 +0900
categories: [Java]
---

### Nested Class   
// 중첩 클래스   
   
// 외부 클래스 정의 내부에 정의된 또 다른 클래스   
// - 내부 (inner) 클래스라고 하며, 외부 (outer) 클래스의 멤버가 됨   
// -- 논리적 그룹화를 위한 것   
// - 내부 클래스는 보통의 클래스와 다르게 private 또는 protected 클래스가 될 수 있음   
// - 일반적으로 내부 클래스는 외부 클래스의 필드와 관련된 작업을 처리   
- Another class defined inside an outer class definition   
  - It is called the inner class, and it becomes a member of the outer class   
    - For logical grouping   
  - Inner classes can be private or protected classes, unlike normal classes   
  - In general, the inner class handles tasks associated with the fields of the outer class   
   
// non-static 중첩 클래스   
// - 외부 클래스의 객체가 생성된 이후 사용 가능 (외부 클래스의 객체와 연관)   
// - 객체 생성 방법은 `외부클래스객체변수.new 내부클래스()`   
// - 메소드는 `this` 외에 외부 클래스 객체의 참조 (`외부클래스.this`) 를 가지고 있음   
// - 외부 클래스의 모든 멤버에 접근할 수 있음   
// static 중첩 클래스   
// - 외부 클래스의 객체 생성과 무관하게 사용 가능   
// - 외부 클래스의 정적 멤버에 접근할 수 있음   
- non-static Nested Class   
  - Available after objects in an outer class are created (associated with objects in an outer class)   
  - The object generation method is `outerClassObjectVariable.new InnerClass()`   
  - In addition to `this`, the method has a reference to an outer class object (`outerClass.this`)   
  - Access to all members of an outer class   
- static Nested Class   
  - Available independently of object creation in outer classes   
  - Access to static members of an outer class   
   
<br />
### Refer to fields of the same name in the nested class   
// 중첩 클래스에서 같은 이름의 필드 참조하기   
   
```java
class OuterClass {
    public int x = 0;

    // non-static 내부 클래스
    // non-static Inner Class
    class InnerClass {
        public int x = 1;

        void methodInnerClass(int x) {
            System.out.println("x = " + x);    // Parameter x
            System.out.println("this.x = " + this.x);    // x in the InnerClass
            System.out.println("OuterClass.this.x = " + OuterClass.this.x);    // x in the OuterClass
        }
    }
}

public class Main {
    public static void main(String args[]) {
        // 외부 클래스 객체 생성
        // Creating an OuterClass Object
        OuterClass oc = new OuterClass();
        // 내부 클래스 객체 생성
        // Creating an InnerClass Object
        OuterClass.InnerClass ic = oc.new InnerClass();
        ic.methodInnerClass(2);
    }
}
```
   
- Result   
   
```
x = 2
this.x = 1
OuterClass.this.x = 0
```

<br />
### Example of using an internal class
// 내부 클래스의 사용 예시

```java
import java.util.Iterator;

public class NestedClassTest {
    private final static int SIZE = 15;
    private int[] data = new int[SIZE];

    public NestedClassTest() {
        for (int i = 0; i < SIZE; i++)
            data[i] = i;
    }

    public void printEven() {
        EvenIterator iterator = this.new EvenIterator();
        while (iterator.hasNext())
            System.out.print(iterator.next() + " ");
        System.out.println();
    }

    private class EvenIterator implements Iterator<Interger> {
        private int nextIndex = 0;

        public boolean hasNext() {
            return (nextIndex <= SIZE - 1);
        }

        public Integer next() {
            // data[nextIndex] 는 NestedClassTest.this.data[nextIndex] 와 동일함. 클래스 이름과 this가 생략됨
            // data[nextIndex] is the same as NestedClassTest.this.data[nextIndex]. Class name and this are omitted
            Integer ret = Integer.valueOf(data[nextIndex]);
            nextIndex += 2;
            return ret;
        }
    }

    public static void main(String args[]) {
        NestedClassText nc = new NestedClassTest();
        nc.printEven();
    }
}
```

- Result

```
0 2 4 6 10 12 14
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
