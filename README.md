# How to download Open JDK 13 for MacOS

Oracle [changed its license terms for Java](https://www.oracle.com/technetwork/java/javase/overview/oracle-jdk-faqs.html)
in April 2019 and it seems that
restrictions on commercial use have increased. It seems like the standard
Java distribution requires payment now if you're a developer. I'm not totally 
sure, but I decided to download and install
[OpenJDK 13](https://openjdk.java.net), which is still free,
on my MacOS machine. The Oracle instructions
don't seem to cover MacOS, so here's my method.

I only need to run Java programs. I'm not a Java developer so let me know if anything
here is wrong.

## Go to openjdk.java.net and download the MacOS version

* Visit [OpenJDK 13](https://openjdk.java.net) and download the **macOS/x64** option. 
It's big, over 300MB.

I assume this leaves the file `openjdk-13_osx-x64_bin.tar` in your `~/Downloads` directory.

## Extract the contents of the archive

* Double-click the file `openjdk-13_osx-x64_bin.tar`.

It gets extracted into a directory named `jdk-13.jdk`.

## Move it to /Library/Java/JavaVirtualMachines/

Drop into your terminal:

* In Finder, choose **Applications > Utilities > Terminal**.

The terminal prompt appears.

* Change to the Downloads directory:

```bash
$ cd ~/Downloads
```

* And move it to the `/Library/Java/JavaVirtualMachines/` directory. 
You'll be asked for your system password.

```bash
$ sudo mv jdk-13.jdk /Library/Java/JavaVirtualMachines/
```

That's it! You may want to ensure it's been copied to the right place.

## Ensure the Java compiler and interpreter run

* Run `java` to check the version of the bytecode interpreter:

```bash
$ java -version
```

You should get something like this:

```bash
openjdk version "13" 2019-09-17
```

* Run `javac` to check the version of the compiler:

```bash
$ javac -version
```

And you'll get a terser message:

```
javac 13
```

## Bonus task: compile and run a program

Just to make sure the toolchain is all there, I wrote a hello world
program, compiled it, and executed i:

* Create the following text file named `hello.java`:

```java
class hello {
	public static void main(String args[]){
	System.out.println("hello, world");
 }
}
```

* Run javac on it to produce an executable:

```bash
$ javac hello.java
```

There's no output from the compiler if all goes well.

* Execute the program:

Now run it:

```bash
$ java hello
```

And get the evergreen response:

```
hello, world.
```


## Exit terminal

Now feel free to close the the Terminal or type `exit` and the prompt and press Enter.

```
$ exit
```
