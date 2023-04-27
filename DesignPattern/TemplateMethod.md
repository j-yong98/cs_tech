템플릿 메소드 패턴 (Template Method Pattern)
=
템플릿 메소드 패턴이란?
-
- 어떤 작업을 처리하는 코드에서 동일한 부분과 다른 부분을 분리해 중복을 최소화 하는 패턴
- 부모 클래스를 상속 받아 자식 클래스들이 특정(다른 부분)을 오버라이드(재정의)할 수 있도록 하는 패턴

예제
-
~~~
public abstract class Parent() {
    // 코드의 중복되는 부분을 선언한다.
    public void excute() {
        long start = System.currentTimeMillis();
        call();
        long end = System.currentTimeMillis();
        long res = end - start;
        System.out.println("걸린 시간 : " + res);
    }
    
    //자식 클래스들이 재정의 하는 부분
    protected abstract void call();
}

public class Child1() extends Parent {
    @Override
    protected void call() {
        System.out.println("Child 1 call");
    }
}

public class Child2() extends Parent {
    @Override
    protected void call() {
        System.out.println("Child 2 call");
    }
}
~~~

~~~
/**
     * 템플릿 메서드 패턴 적용
     */
    @Test
    void templateMethodV1() {
        Parent template1 = new Child1();
        Parent template2 = new Child2();
        template1.execute();
        template2.execute();
    }
    //익명 클래스 ver
    @Test
    void templateMethodV2() {
        Parent template1 = new Parent() {
            @Override
            protected void call() {
                System.out.println("Child 1 call");
            }
        };
        template1.execute();
        Parent template2 = new Parent() {
            @Override
            protected void call() {
                System.out.println("Child 2 call");
            }
        };
        template2.execute();
    }
~~~
- 상속과 다형성을 이용해 공통 부분과 다른 부분을 분리하여 실행할 수 있다.
- 하지만 해당 패턴은 상속을 이용하기 때문에 자식은 부모에 의존한다는 단점이 있다.