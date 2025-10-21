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
public LoanUISystem();
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
private System.Void AcceptLoanOffer();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private RequestLoanOffer(System.Int32 amount) : System.Void`  

```csharp
private System.Void RequestLoanOffer(System.Int32 amount);
```

- `private ResetLoanOffer() : System.Void`  

```csharp
private System.Void ResetLoanOffer();
```


## Nested types

- `Game.UI.InGame.LoanUISystem+LoanWriter`  

