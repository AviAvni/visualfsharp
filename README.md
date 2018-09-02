# OPENFSHARP COntribution to the compiler workshop

## 1st Task

In this task you'll implement a new feature that trasform
```
type I3 = int * * 3
```

To
```
type I3 = int * int * int
```

Think in what phase of the compiler this need to be done?
```
Source -> Tokenizer -> Tokens -> Parser -> AST -> Type Checker -> TAST -> Optimizer -> TAST -> Code Generator -> IL
```

Follow the instructions to complete this task

1. Open ast.fs and look at SynType.Tuple discriminated union
2. Open pars.fsy and locate tupleType parsing rule 
3. Add a rule to parse type like: int * * 3 and transform it to : int, int, int
4. Build the compiler
5. Try in fsi