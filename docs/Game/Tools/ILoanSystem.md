# Game.Tools.ILoanSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface ILoanSystem
{
    public Game.Tools.LoanInfo CurrentLoan { get; }
    public System.Int32 Creditworthiness { get; }

    public abstract System.Void ChangeLoan(System.Int32 amount);
    public abstract Game.Tools.LoanInfo RequestLoanOffer(System.Int32 amount);
}
```


## Properties

- `public Game.Tools.LoanInfo CurrentLoan { get }`  

```csharp
public Game.Tools.LoanInfo CurrentLoan { get; }
```

- `public System.Int32 Creditworthiness { get }`  

```csharp
public System.Int32 Creditworthiness { get; }
```


## Methods

- `public abstract ChangeLoan(System.Int32 amount) : System.Void`  

```csharp
public abstract System.Void ChangeLoan(System.Int32 amount);
```

- `public abstract RequestLoanOffer(System.Int32 amount) : Game.Tools.LoanInfo`  

```csharp
public abstract Game.Tools.LoanInfo RequestLoanOffer(System.Int32 amount);
```


