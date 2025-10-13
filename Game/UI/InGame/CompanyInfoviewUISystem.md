# Game.UI.InGame.CompanyInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CompanyInfoviewUISystem : Game.UI.InGame.InfoviewUISystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Unity.Entities.EntityQuery m_CommercialQuery;
    private Unity.Entities.EntityQuery m_IndustrialQuery;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_CommercialProfitability;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_IndustrialProfitability;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_OfficeProfitability;
    private Game.UI.InGame.CompanyInfoviewUISystem+TypeHandle __TypeHandle;
    private static const System.String kGroup;

    protected System.Boolean Active { protected get; }

    public CompanyInfoviewUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Game.UI.InGame.IndicatorValue GetCommercialProfitability();
    private Game.UI.InGame.IndicatorValue GetIndustrialProfitability();
    private Game.UI.InGame.IndicatorValue GetOfficeProfitability();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void PerformUpdate();
}
```


## Fields

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Unity.Entities.EntityQuery m_CommercialQuery`  

```csharp
private Unity.Entities.EntityQuery m_CommercialQuery;
```

- `private Unity.Entities.EntityQuery m_IndustrialQuery`  

```csharp
private Unity.Entities.EntityQuery m_IndustrialQuery;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_CommercialProfitability`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_CommercialProfitability;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_IndustrialProfitability`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_IndustrialProfitability;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_OfficeProfitability`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_OfficeProfitability;
```

- `private Game.UI.InGame.CompanyInfoviewUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.CompanyInfoviewUISystem+TypeHandle __TypeHandle;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Properties

- `protected System.Boolean Active { protected get }`  

```csharp
protected System.Boolean Active { protected get; }
```


## Constructors

- `public CompanyInfoviewUISystem()`  

```csharp
public CompanyInfoviewUISystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private GetCommercialProfitability() : Game.UI.InGame.IndicatorValue`  

```csharp
private Game.UI.InGame.IndicatorValue GetCommercialProfitability();
```

- `private GetIndustrialProfitability() : Game.UI.InGame.IndicatorValue`  

```csharp
private Game.UI.InGame.IndicatorValue GetIndustrialProfitability();
```

- `private GetOfficeProfitability() : Game.UI.InGame.IndicatorValue`  

```csharp
private Game.UI.InGame.IndicatorValue GetOfficeProfitability();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual PerformUpdate() : System.Void`  

```csharp
protected virtual System.Void PerformUpdate();
```


## Nested types

- `Game.UI.InGame.CompanyInfoviewUISystem+TypeHandle`  

