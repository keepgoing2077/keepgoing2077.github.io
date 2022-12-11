## 线程池
- 线程池相关的类  
ExecutorService 接口，ThreadPoolExecutor类，Executors工具类  
- 常见的用法  
ExecutorService pool = Executors.newCachedThreadPool();  
使用其execute(Runnable r)方法  
```
class ThreadPoolDemo{
    public static void main(String[] args){
        ExecutorService pool = Executors.newCachedThreadPool();
        MyTask t1 = new Mytask(5);
        MyTask t2 = new MyTask(7);
        MyTask t3 = new MyTask(8);
        pool.execute(t1);
        pool.execute(t2);
        pool.execute(t3);
        pool.shutdown();
    }
}
class MyTask implements Runnable{...}
```

## Timer
- 使用java.util.Timer类
重复某件事  
```
import java.util.*;
class TimerTest{
    public static void main(String[] args){
        Timer timer = new Timer("display");
        TimerTask task = new MyTask();
        timer.schedule(task, 1000, 1000);
    }
}
class MyTask extends TimerTask{...}
```
- 使用javax.swing.Timer类
重复执行ActionListener  
```
import javax.swing.Timer;
class TimerSwing extends JFrame{
    Timer timer;
    public void init(){
    ...;
    timer = new Timer(1000, (e)->{
        setTitle(new java.util.Date().toString());
    });
    timer.start();
    }
    public static void main(String[] args){...}
}
```
