# OPENFSHARP Contribution to the compiler workshop

## 3rd Task

In this task you'll extend the feature from the 2st task to be able to compile and run code like this
```
type Vect<'n, 'a> = 'a * 'n

type I3 = Vect<3, int>

let i3 : I3 = 1, 2, 3

type Vect<'n, 'm, 'a> = 'a * 'n * 'm

type I33 = Vect<3, 3, int>

let i33 : I33 = 1, 2, 3, 4, 5, 6, 7, 8, 9
```

Think in what phase of the compiler this need to be done?
```
Source -> Tokenizer -> Tokens -> Parser -> AST -> Type Checker -> TAST -> Optimizer -> TAST -> Code Generator -> IL
```

Follow the instructions to complete this task

### Part 1 type cheking

1. Open ConstraintSolver.fs locate SolveTypeEqualsType debug around this code
2. Refactor the multiplication of types and call it when a tuple with generic type parameter inferred