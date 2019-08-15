# Static Keyword

The **static** keyword denotes that a member variable, or method, can be accessed without requiring an instantiation of the class to which it belongs.

In simple terms, it means that you can call a method, even if you've never created the object to which it belongs! Every time you run a stand-alone application (which requires a static main method), the virtual machine can call the main method without creating a new application object. Of course, unless the application's methods are all static, you will need to create an instance of it at some point.

With regard to member variables, it means that they can be read from, and written to, without creating an object. You may have noticed that many classes create constants that can be read, without creating an object.

`static final int VERSION = 2;`

Static member variables are shared by all instances of the class to which they belong. When writing classes, this can be a handy feature. Consider the following example, where a counter is used to track how many myObject instantiations have taken place.

```java
public class myObject
{
    static int objectCount = 0;
    public myObject(){
        objectCount++;
    }
    public String toString(){
        return new String ("There are " + objectCount + " objects");
    }
}
```

As each new *myObject* is created, the counter increments. If you were writing an Internet server application, you could track how many concurrent connections existed (remembering that you'd have to include in the destructor or at the end of the connection code a decrement to your count). When used correctly, static member variables and methods can be quite useful!

 