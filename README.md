# OPENFSHARP Contribution to the compiler workshop

## 4th Task

Q: What is the problem with tring to implement Vector as tuple?
A: Can't implement generic method that manipulate Vector

Q: How we can solve this problem?
A: Implement it as discriminated union like in Idris


In this task you'll extend the feature from the 3st task to be able to compile and run code like this
```
type Vect<'n, 'a> = | Nil | Cons of 'a * Vect<'n - 1, 'a>

let v2 : Vect<2, int> = Cons(1, Cons(2, Nil))

let v2 : Vect<2, int> = Cons(1, Cons(2, Cons(3, Nil)))
```

Think in what phase of the compiler this need to be done?
```
Source -> Tokenizer -> Tokens -> Parser -> AST -> Type Checker -> TAST -> Optimizer -> TAST -> Code Generator -> IL
```

Follow the instructions to complete this task

### Part 1

1. Based on 2nd task implement parsing of types like 'n - 1
2. Refactor the logic for calculating multiplication to support additional operations
3. Implement type checking
4. Raise error when nat is less then 0