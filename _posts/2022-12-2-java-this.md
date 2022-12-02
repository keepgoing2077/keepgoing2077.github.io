# [Java]this的使用
- 使用this解决局部变量与域同名的问题  
```
    Person(int age, String name){  
        this.age = age;  
        this.name = name;  
     }
```     
     
- 构造方法中, 用this调用另一构造方法  
```
    Person(){  
        this(0, "");    
        ...    
    }
```
