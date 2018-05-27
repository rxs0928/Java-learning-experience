java 中经常采用的异常处理语句为
  try {
          /**/
            }
        } catch (Exception e) {
            System.out.println(e.toString());
            System.out.println(e.getMessage());
            //或者是 System.out.println(e.toString());        e.printStackTrace();
            return "";
        }
下面介绍Exception e中e.getMessage()、e.toString()和e.printStackTrace()方法的区别：

e.toString()获取的信息包括异常类型和异常名称，

e.getMessage()只是获取了异常名称字符串， 比如说NullPoint ,就是指空指针.

e.printStackTrace() 会打出详细异常,异常名称,出错位置,便于调试。一般一个异常至少几十行

示例代码1：
public class TestInfo {
    private static int m = 0;
    public static void main(String[] args) {
        System.out.println("test exception");
        try {
            m = 899/0;
        } catch (Exception e) {
            System.out.println(e.toString());
            System.out.println(e.getMessage());
        }
    }
}
输出结果：
java.lang.ArithmeticException: / by zero
/ by zero

示例代码2：
public class TestInfo {
    private static String str =null;
    public static void main(String[] args) {
        System.out.println("test exception");
        try {
            if(str.equals("name")){
                System.out.println("test exception");
            }
        } catch (Exception e) {
            System.out.println(e.toString());
            System.out.println(e.getMessage());
        }
    }
}
输出结果：
java.lang.NullPointerException
null
