一:==的特殊使用
当使用双引号创建字符串对象的时候，系统会检查该字符串是否在字符串常量池中存在(节省内存空间)
不存在:创建
存在:不会重新创建，而是直接复用
public class Demo3{
public static void main(String[] args) {

String s1 = new String( original: "abc");//开辟一个新的内存空间
String s2 = "abc" ; //从常量池中取
byte[] bytes = {97，98，993};
String s3 = new String (bytes);//开辟一个新的内存空间
String s4 = "abc"; //从常量池中取
System.out.println(s1 == s2);// false
system.out.println(s1 == s3) ;//false
system.out.println(s1 == s4);// false
System.out.println(s2 == s3) ;// false
system.out.println(s2 ==s4);//true
    }
}

以""方式给出的字符串(string s2 = "abc")，只要字符序列相同(顺序和大小写)，无论在程序代码中出现几次，JVM都只会建立一个String 对象，并在字符串常量池中维护
String s1 = "abc";
String s2 = "abc";


二:String类中的equals()方法-->只能针对引用类型
比较的是具体的数值(内容)
public class Demo4{
public static void main(String[] args) {
String s1 = "abc" ;
String s2 = new String("abc");
byte[] bytes = {97,98,99};
String s3 = new String(bytes) ;
char[] chars = {'a','b','c'};
String s4 = new String(chars);
System.out.println(s1.equals(s2));//true
system.out.println(s1.equals(s3)) ;//true
system.out.println(s1.equals(s4));//true
}
}

三:
String s1 = "hello" ;
string s2 = "world" ;
String s3 = "java";
//s1+s2会得到一个新的地址值,然后再+s3又会得到一个新的地址值,最后将这个数值赋值给一个新的地址值s4
String s4 = s1 +s2 + s3;//将3个对象的地址值进行操作
System.out.println(s4);//helloworldjava
system.out.println("---------------");
StringBuilder sb1 = new StringBuilder("hello");
StringBuilder sb2 =new StringBuilder("world") ;
StringBui1der sb3 = new StringBuilder("java");
System.out. println(sb1 .append(sb2). append(sb3));
}

