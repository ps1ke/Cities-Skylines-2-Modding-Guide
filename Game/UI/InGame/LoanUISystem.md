# Game.UI.InGame.LoanUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

## Code

```csharp
public class LoanUISystem : Game.UI.UISystemBase
{
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_LoanLimitBinding;
    private Colossal.UI.Binding.GetterValueBinding<Game.Tools.LoanInfo> m_CurrentLoanBinding;
    private Colossal.UI.Binding.GetterValueBinding<Game.Tools.LoanInfo> m_LoanOfferBinding;
    private Game.Tools.ILoanSystem m_LoanSystem;
    private System.Int32 m_RequestedOfferDifference;
    private static const System.String kGroup;

    public LoanUISystem();

    private System.Int32 <OnCreate>b__6_0();
    private Game.Tools.LoanInfo <OnCreate>b__6_1();
    private Game.Tools.LoanInfo <OnCreate>b__6_2();
    private System.Void AcceptLoanOffer();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
    private System.Void RequestLoanOffer(System.Int32 amount);
    private System.Void ResetLoanOffer();
}
```


## Fields

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_LoanLimitBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_LoanLimitBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.Tools.LoanInfo> m_CurrentLoanBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.Tools.LoanInfo> m_CurrentLoanBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.Tools.LoanInfo> m_LoanOfferBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.Tools.LoanInfo> m_LoanOfferBinding;
```

- `private Game.Tools.ILoanSystem m_LoanSystem`  

```csharp
private Game.Tools.ILoanSystem m_LoanSystem;
```

- `private System.Int32 m_RequestedOfferDifference`  

```csharp
private System.Int32 m_RequestedOfferDifference;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Constructors

- `public LoanUISystem()`  

```csharp
[Preserve]
	public LoanUISystem()
	{
	}
```


## Methods

- `private <OnCreate>b__6_0() : System.Int32`  

```csharp
private System.Int32 <OnCreate>b__6_0();
```

- `private <OnCreate>b__6_1() : Game.Tools.LoanInfo`  

```csharp
private Game.Tools.LoanInfo <OnCreate>b__6_1();
```

- `private <OnCreate>b__6_2() : Game.Tools.LoanInfo`  

```csharp
private Game.Tools.LoanInfo <OnCreate>b__6_2();
```

- `private AcceptLoanOffer() : System.Void`  

```csharp
private void AcceptLoanOffer()
	{
		m_LoanSystem.ChangeLoan(m_LoanSystem.CurrentLoan.m_Amount + m_RequestedOfferDifference);
		m_RequestedOfferDifference = 0;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_LoanSystem = base.World.GetOrCreateSystemManaged<LoanSystem>();
		AddBinding(m_LoanLimitBinding = new GetterValueBinding<int>("loan", "loanLimit", () => m_LoanSystem.Creditworthiness));
		AddBinding(m_CurrentLoanBinding = new GetterValueBinding<LoanInfo>("loan", "currentLoan", () => m_LoanSystem.CurrentLoan, new LoanWriter()));
		AddBinding(m_LoanOfferBinding = new GetterValueBinding<LoanInfo>("loan", "loanOffer", () => m_LoanSystem.RequestLoanOffer(m_LoanSystem.CurrentLoan.m_Amount + m_RequestedOfferDifference), new LoanWriter()));
		AddBinding(new TriggerBinding<int>("loan", "requestLoanOffer", RequestLoanOffer));
		AddBinding(new TriggerBinding("loan", "acceptLoanOffer", AcceptLoanOffer));
		AddBinding(new TriggerBinding("loan", "resetLoanOffer", ResetLoanOffer));
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		base.OnGameLoaded(serializationContext);
		m_RequestedOfferDifference = 0;
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_LoanLimitBinding.Update();
		m_CurrentLoanBinding.Update();
		m_LoanOfferBinding.Update();
	}
```

- `private RequestLoanOffer(System.Int32 amount) : System.Void`  

```csharp
private void RequestLoanOffer(int amount)
	{
		LoanInfo loanInfo = m_LoanSystem.RequestLoanOffer(amount);
		LoanInfo currentLoan = m_LoanSystem.CurrentLoan;
		m_RequestedOfferDifference = loanInfo.m_Amount - currentLoan.m_Amount;
	}
```

- `private ResetLoanOffer() : System.Void`  

```csharp
private void ResetLoanOffer()
	{
		m_RequestedOfferDifference = 0;
	}
```


## Nested types

- `Game.UI.InGame.LoanUISystem+LoanWriter`  

