# 1-3 List interface
- JCF 는 List 라는 interface 를 정의하고 ArrayList, LinkedList 라는 두 구현 클래스를 제공합니다.
- interface는 List가 된다는 의미가 무엇인지를 정의합니다.
- 이 interface를 구현하는 클래스는 add, get, remove 와 약 20가지 메서드를 포함한 특정 메서드 집합을 제공해야합니다.
- ArrayList, LinkedList 클래스는 이러한 메서드를 제공하므로 상호교환할 수 있습니다.
- List로 동작하는 메서드는 ArrayList, LinkedList 또는 List 를 구현하는 어떤 객체와도 잘 동작합니다.

```Java
public class ListClientExample {
    private List list;

    public ListClientExample() {
        list = new LinkedList();
    }

    private List getList() {
        return list;
    }

    public static void main(String[] args) {
        ListClientExample lce = new ListClientExample();
        List list = lce.getList();
        System.out.println(list);
    }
}
```
- 위 예제에서 중요한 내용은 필요한 경우가 아니면 ArrayList, LinkedList 클래스를 직접 사용하지 않고 List interface를 사용하는 것입니다.
- 이러한 스타일을 인터페이스 기반 프로그래밍이라고 합니다. 여기서의 인터페이스는 자바의 interface가 아니라 일반적인 의미의 interface를 의미합니다.