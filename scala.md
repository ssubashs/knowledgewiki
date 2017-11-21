### Variance

 The problem here is that Empty is a Maybe[Nothing] and a Maybe[Nothing] is not a subtype of Maybe[Int] (by default invariance) even though Int is a subtype of Nothing.


    val mayBe:Maybe[Int] = Empty;
    sealed trait Maybe[A]
    final case class Full[A](value: A) extends Maybe[A]
    final case object Empty extends Maybe[Nothing]



  - [ ] A type Foo[T] is invariant in terms of T, meaning that the types Foo[A] and Foo[B] are unrelated regardless of the relationship between A and B. This is the default variance of any generic type in Scala.

  - [ ] A type Foo[+T] is covariant in terms of T, meaning that Foo[A] is a supertype of Foo[B] if A is a supertype of B. Most Scala collection classes are covariant in terms of their contents. We’ll see these next chapter.

  - [ ] A type Foo[-T] is contravariant in terms of T, meaning that Foo[A] is a subtype of Foo[B] if A is a supertype of B. The only example of contravariance that I am aware of is function arguments.
