# Game.Tools.LoanInfo

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.Tools.LoanInfo>`  

## Code

```csharp
public sealed struct LoanInfo : System.IEquatable<Game.Tools.LoanInfo>
{
    public System.Int32 m_Amount;
    public System.Single m_DailyInterestRate;
    public System.Int32 m_DailyPayment;

    public System.Boolean Equals(Game.Tools.LoanInfo other);
}
```


## Fields

- `public System.Int32 m_Amount`  

```csharp
public System.Int32 m_Amount;
```

- `public System.Single m_DailyInterestRate`  

```csharp
public System.Single m_DailyInterestRate;
```

- `public System.Int32 m_DailyPayment`  

```csharp
public System.Int32 m_DailyPayment;
```


## Methods

- `public Equals(Game.Tools.LoanInfo other) : System.Boolean`  

```csharp
public bool Equals(LoanInfo other)
	{
		if (m_Amount == other.m_Amount && m_DailyInterestRate.Equals(other.m_DailyInterestRate))
		{
			return m_DailyPayment == other.m_DailyPayment;
		}
		return false;
	}
```


