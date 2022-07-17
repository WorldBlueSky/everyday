



## Scanner类中的 next、nextLine 问题



在写一个题目的时候，发现了一个问题。next() 、nextLine()、nextInt() 之间的连续使用问题



连续多行输入，最好全部使用nextLine,最后需要什么类型在进行各自转换。



有一个很严重的问题



nextLine 跟在 nextInt 、nextDouble、next 后面会自动读取 回车键结束符作为 一个输入。

```java
    public static void main(String[] args) {
        Scanner sc =  new Scanner(System.in);
        int n =sc.nextInt();
        String str = sc.nextLine();
    }
```



程序运行结果

![1657247536718](C:\Users\rain7\AppData\Roaming\Typora\typora-user-images\1657247536718.png)



输入了一个6，点击回车，结束了程序，因为 nextLine 读取了回车符，相当于打印一个空行，结束程序。



这种写法尽量不要写，都写成nextLine,在根据自己需要转化成 自己想要的类型

```java
    public static void main(String[] args) {
        Scanner sc =  new Scanner(System.in);
        int n =Integer.parseInt(sc.nextLine());
        String str = sc.nextLine();
    }
```



程序运行结果

![1657247640295](C:\Users\rain7\AppData\Roaming\Typora\typora-user-images\1657247640295.png)





还有一种解决方法，就是将nextLine 换成next,next 只读取输入的字符，不读取回车，空格这类

```java
    public static void main(String[] args) {
        Scanner sc =  new Scanner(System.in);
        int n =sc.nextInt();
        String str = sc.next();
    }
```



程序运行结果

![1657247982636](C:\Users\rain7\AppData\Roaming\Typora\typora-user-images\1657247982636.png)