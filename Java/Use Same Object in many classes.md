* Suppose 2 classes StatementGenerate and Main, use c1 object of CustomerInfo.
* If you want other class methods that they can access c1 object details, create `object variable` in that class and create a `constructor of object variable` for same.

CustomerInfo.java
```java
public class CustomerInfo {
    private String name;

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }
}
```

StatementGenerate.java
```java
public class StatementGenerate {
    private CustomerInfo c1;

    public StatementGenerate(CustomerInfo c1) {
        this.c1 = c1;
    }

    public void statement() {
        System.out.printf("Name: %s", c1.getName());
    }
}
```

Main.java
```java
public class Main {
    private CustomerInfo c1;

    public Main(CustomerInfo c1) {
        this.c1 = c1;
    }

    public static void Main(String[] args) {
        CustomerInfo c1 = new CustomerInfo();
        StatementGenerate sg = new StatementGenerate(c1);

        c1.setName("Aansh Ojha");
        sg.statement();
    }
}
```