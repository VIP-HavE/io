File类是Java.io包中用来操作文件的类，通过调用File类的方法，可实现创建、删除、重命名文件等功能。使用File类的对象可以获取文件的基本信息，如文件所在目录、文件名、文件大小、文件的修改时间等。
# 一、创建文件对象
1. File（String pathname）

```java
File file = new File("C:/java.text");
```

2. File（String parent, String Child）
```java
File file = new File("C:/demo/", "java.text");
```
3. File（File f, String Child）
```java
File folder = new File("C:/demo/");
File file = new File(folder , "java.text");
```
# 二，File的使用
## 1、文件操作
<table>
	<tr>
	    <th>文件操作</th>
	    <th>返回值</th>
	    <th>说明</th>
	</tr >
	<tr >
	    <td>exists()</td>
	    <td>boolean</td>
	    <td>判断文件(夹)是否存在</td>
	</tr>
	<tr >
	    <td>createNewFile()</td>
	    <td>boolean</td>
	    <td>当前文件不存在时创建一个新的空文件</td>
	</tr>
	<tr >
	    <td>isFile()</td>
	    <td>boolean</td>
	    <td>判断是否为文件</td>
	</tr>
	<tr >
	    <td>canReaed()</td>
	    <td>boolean</td>
	    <td>判断文件是否可读取</td>
	</tr>
	<tr >
	    <td>canWrite()</td>
	    <td>boolean</td>
	    <td>判断文件是否可写入</td>
	</tr>
	<tr >
	    <td>canExecute()</td>
	    <td>boolean</td>
	    <td>判断文件是否可通过其抽象名称执行</td>
	</tr>
	<tr >
	    <td>delete()</td>
	    <td>boolean</td>
	    <td>删除指定文件(夹)</td>
	</tr>
	<tr >
	    <td>getAbsoluteFile()</td>
	    <td>File</td>
	    <td>返回抽象路径名的绝对路径名形式</td>
	</tr>
	<tr >
	    <td>getAbsolutePath()</td>
	    <td>String</td>
	    <td>返回文件的绝对路径</td>
	</tr>
	<tr >
	    <td>getName()</td>
	    <td>String</td>
	    <td>获取文件(夹)的名称</td>
	</tr>
	<tr >
	    <td>getParent()</td>
	    <td>String</td>
	    <td>获取文件的父路径</td>
	</tr>
	<tr >
	    <td>getPath()</td>
	    <td>String</td>
	    <td>获取路径名</td>
	</tr>
	<tr >
	    <td>getFreeSpace()</td>
	    <td>long</td>
	    <td>返回抽象路径名指定分区中未分配的字节数</td>
	</tr>
	<tr >
	    <td>getTotalSpace()</td>
	    <td>long</td>
	    <td>返回抽象路径名指定分区的大小</td>
	</tr>
	<tr >
	    <td>length()</td>
	    <td>long</td>
	    <td>获取文件的长度（字节单位）</td>
	</tr>
	<tr >
	    <td>isHidden()</td>
	    <td>boolean</td>
	    <td>判断文件是否是隐藏文件</td>
	</tr>
	<tr >
	    <td>lastModified()</td>
	    <td>long</td>
	    <td>获取文件最后修改时间</td>
	</tr>
	<tr >
	    <td>renameTo()</td>
	    <td>boolean</td>
	    <td>文件重命名</td>
	</tr>
	<tr >
	    <td>setLastModified(long time)</td>
	    <td>boolean</td>
	    <td>设置文件(夹)的最后一次修改时间</td>
	</tr>
	<tr >
	    <td>setReadOnly()</td>
	    <td>boolean</td>
	    <td>将文件或文件夹设置为只读</td>
	</tr>
</table>

## 2、文件夹操作
<table>
	<tr>
	    <th>方法</th>
	    <th>返回值</th>
	    <th>说明</th>
	</tr >
	<tr >
	    <td>isDirectoty()</td>
	    <td>boolean</td>
	    <td>判断是不是文件夹</td>
	</tr>
	<tr >
	    <td>list()</td>
	    <td>String[]</td>
	    <td>返回字符串数组<br/>这些字符串指定此抽象路径名表示目录中的文件和目录</td>
	</tr>
	<tr >
	    <td>list(FilenameFilter filter)</td>
	    <td>String[]</td>
	    <td>返回字符串数组<br/>这些字符串指定此抽象路径名表示目录中满足指定过滤器的文件和目录</td>
	</tr>
	<tr >
	    <td>listFiles()</td>
	    <td>File[]</td>
	    <td>返回抽象路径名数组<br/>这些路径名表示此抽象路径名表示目录中的文件</td>
	</tr>
	<tr >
	    <td>listFiles(Fileter filter)</td>
	    <td>File[]</td>
	    <td>返回抽象路径名数组<br/>这些路径名表示此抽象路径名表示目录中的满足指定过滤器的文件和目录</td>
	</tr>
	<tr >
	    <td>listFiles(FilenameFilter filter)</td>
	    <td>File[]</td>
	    <td>返回抽象路径名数组<br/>这些路径名表示此抽象路径名表示目录中的满足指定过滤器的文件和目录</td>
	</tr>
	<tr >
	    <td>mkdir()</td>
	    <td>boolean</td>
	    <td>创建此抽象路径名指定的目录</td>
	</tr>
	<tr >
	    <td>mkdirs()</td>
	    <td>boolean</td>
	    <td>创建此抽象路径名指定的目录，包括所有必需但不存在 的目录</td>
	</tr>
</table>

# 三、代码实践

```java
package Filedemo;
import java.io.File;
import java.io.IOException;

/**
 @author HCY
 @date 2022/2/23 22:29
 @version V1.0
 **/

class FileDemo {
    public static void main(String[] args) throws IOException {
        File file = new File("src/abc.txt");

        //如果文件不存在，则创建文件
        if (!file.exists()) {
            try {
                file.createNewFile();
            } catch (IOException e) {
                e.printStackTrace();
            }
        } else {
           
            //判断文件的属性，都会返回boolean类型的值
            file.canExecute();
            file.canRead();
            file.canWrite();

            //判断当前文件是否存在
            System.out.println(file.exists());

            //该文件是一个标准文件且可读
            if(file.isFile() && file.canRead()){
                //获取文件的名称
                System.out.println(file.getName());
                //获取文件的绝对路径
                System.out.println(file.getAbsolutePath());
                //获取文件的父路径名称，如果文件的路径中只包含文件名称，则显示空
                System.out.println(file.getParent());
                //返回文件绝对路径的规范格式
                System.out.println(file.getCanonicalPath());
                //返回操作系统的文件分割符
                System.out.println(File.separator);
            }
            
            
        }
        
        //无论当前文件是否存在，只要给定具体的路径，都可以返回相应的路径名称
        File file2 = new File("c:/a/b/c");
        System.out.println(file2.getAbsolutePath());
        
        //判断文件是否是文件或者目录
        System.out.println(file2.isDirectory());
        System.out.println(file2.isFile());

 		//list打印地址，listFiles打印文件夹名称
        String[] list = file2.list();
        for(String str:list){
            System.out.println(list.toString());
        }
        System.out.println("---------------");
        File[] files = file2.listFiles();
        for(File f : files){
            System.out.println(f);
        }

        //打印当前文件系统的所有盘符
        File[] files1 = File.listRoots();
        for(int i = 0;i<files1.length;i++){
            System.out.println(files1[i]);
        }

        //创建单级目录
        file2.mkdir();
        //创建多级目录
        file2.mkdirs();

        //循环遍历输出C盘中的所有文件的绝对路径
        //使用递归的方式
        printFile(new File("D:\\Github\\javase"));
    }

    /**
     *
     * 文件在遍历的时候，会出现空指针的问题，原因在于当前文件系统受保护，某些文件没有访问权限，此时会报空指针异常
     * @param file
     */
    public static void printFile(File file){

        if(file.isDirectory()){
            File[] files = file.listFiles();
            for(File f:files){
                printFile(f);
            }
        }else{
            System.out.println(file.getAbsolutePath());
        }

    }
}
```