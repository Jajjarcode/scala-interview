# Scala Interview Utils

This repository is a nice place to maintain the types of questions I like to ask when interviewing for Scala developers. I don't ask all these questions, and usually I just use these as a starting point and expand. That way, even if someone has been informed by their agent in advance what questions previous candidates were asked, it won't help them.

## Subjective Scala Questions
* If you were forced to use Java, but could take any feature from Scala you wanted, what would it be. (Assume Java 8 to avoid everyone saying first class functions). Related: What is your favourite feature of Scala.
* Why did you start using Scala in the first place.
* What would you change in Scala if you could.
* Why do you think some people do not use Scala and instead prefer other JVM languages.

## Alliterations  
* Explain the following terms: `Nil`, `Null`, `None`, `Nothing`
* Explain the following terms: `abstract`, `apply`, `anyval`, `alias`
* Explain the following terms: `copy`, `closure`, `covariance`, `curry`
* Explain the following terms: `literal`, `lazy`, `linearization`, `last`
* Explain the following terms: `extends`, `expression`, `erasure`, `extractor`
* Explain the following terms: `tuple`, `trait`, `tail`, `typeclass`
* Explain the following terms: `map`, `match`, `method`, `manifest`
* Explain the following terms: `super`, `sequence`, `Some`, `sealed`
* Explain the following terms: `val`, `var`, `variance`, `vararg`
* Explain the following terms: `option`, `object`, `override`, `ordered`

## General
* What does the following method signature mean and why would it be useful: `def foo(f : => String)`
* If you wanted to build a List of (many) elements how would you do that in Scala. How about if you knew the size in advance.

## Functional Programming

## Patterns
* Can you briefly describe a typeclass
* Rewrite this Java code using a typeclass style:
```java
public interface Explodable { 
  public void explode();
}
public class Bomb extends Explodable {
  public void explode { System.out.println("boom"); }
}
public class Main {
  public static void main(String args[]) {
    new Bomb().explode();
  }
}
```

## Frameworks
* Describe the actor model briefly
* 

## Concurrency
* Can you suggest a way to improve the following snippet:
```scala
def customer : Future[Customer] = ...
def invoice : Future[Invoice] = ...
for(c <- customer; i <- invoice) { // do stuff }
```
* Given a Future, f, how would you perform an action if the future fails without blocking on the future.
* Given a Future, f that returns A, and a function A => B how would you adapt that so that the caller can receive a B once the future completes.
* If two threads use a shared map, what would happen if both threads are writing and reading to that map?
* If the threads above synchronize on (this) would that make it thread safe?
* How can you make it thread safe?
* If a thread has a monitor and then calls synchronize on that monitor again, what will happen?

## Whiteboard
* Given a function, `def download(url:String):Future[String]`, implement the following function:
  `def downloadAll(urls:Seq[String]):Future[Seq[String]]`
* How many errors can you spot in the following:
```scala
How many errors can you spot in the following:

(assume imports)

public class Foo(String : name) extends BooTrait, MooTrait {

  val time : Long = _
  val id   : UUID = UUID.randomUuid()

  override def toString = s"My name is {name}"

  def newFoo() = new Foo(Random.nextString)
  def newFoo(name : String) = new Foo(name)

  def map(f: String => String) = new Foo(f(name))
  def map(f: String => Int) = new Foo(f(name).toString)

  def whodunnit(person: String = "Professor Plum", weapon: Weapon= Weapon.Candlestick) = {}
  def whodunnit(person: String = "Professor Plum", where: Place = Place.Study) = {}

  def moo(implicit execution: ExecutionContext)(f : => T) : Future[T] = Future { f }

  def zoo(any: Any) = any match {
    case "sammy" => println("my name is sammy")
    case other : String => println("I am not called sammy")
  }

  def voo[A <: Any](a : A) : Unit = println(a)

  def stop : Message = StopExecuting()

  trait Message
  case class StopMessage extends Message
}
```

## Web
* Describe HATEOS and the pros and cons of such an approach

## JVM

## Data Structures
* Can you describe what a priority queue is.
* Can you tell me what a heap is.
* Linked List vs Array - when would you choose which (In an ADT way, not necessarily just in Scala)
