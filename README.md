# OPENFSHARP Contribution to the compiler workshop

## 2nd Task

In this task you'll extend the feature from the 1st task to be able to compile and run code like this
```
type I3 = int * 3

let i3 : I3 = 1, 2, 3

type I33 = int * 3 * 3

let i33 : I33 = 1, 2, 3, 4, 5, 6, 7, 8, 9

type Three = 3

type IThreeThree = int * Three * Three

let iThreeThree : IThreeThree = 1, 2, 3, 4, 5, 6, 7, 8, 9
```

Think in what phase of the compiler this need to be done?
```
Source -> Tokenizer -> Tokens -> Parser -> AST -> Type Checker -> TAST -> Optimizer -> TAST -> Code Generator -> IL
```

Follow the instructions to complete this task

### Part 1 parsing

1. Open ast.fs locate the SynType discriminated union add the Nat option and implement the Range property
2. Open pars.fsy locate atomType rule change the result of parsing rawConstant to to return SynType.Nat in case that rawConstant is SynConst.Int32

### Part 2 type cheking

1. Open tast.fs locate TType discriminated union add TType_nat option and implement GetAssemblyName and ToString methods
2. Open TypeChecker.fs locate TcTypeOrMeasure function and implement the conversion between SynType.Nat to TType_nat
3. Then locate TcTyconDefnCore_CheckForCyclicAbbreviations function and implement that TType_nat is ignored in checking cycles in abbreviations
4. Then locate TcTypesAsTuple function and implement multiplication of types

### Part 3

1. Open the following files and check how I changed them
TastOps.fs
TastPickle.fs - Ignoring serialization of TAST 
NicePrint.fs - Pretty print nat type
ConstraintSolver.fs - Ignoring constraits
PostInferenceChecks.fs - Ignoring constraits
IlxGen.fs - Emit Nat as integer
Symbol.fs - Calculate hash for nat type
