# Game.UI.InGame.ProfitabilitySection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ProfitabilitySection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.Simulation.TaxSystem m_TaxSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Unity.Entities.EntityQuery m_DistrictBuildingQuery;
    private Unity.Entities.EntityQuery m_ProcessQuery;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    public Unity.Collections.NativeArray<System.Int32> m_Results;
    private Game.UI.InGame.CompanyProfitability <profitability>k__BackingField;
    private Unity.Collections.NativeArray<Unity.Mathematics.int2> m_Factors;
    private Unity.Collections.NativeList<Game.UI.InGame.FactorInfo> <profitabilityFactors>k__BackingField;
    private Game.UI.InGame.ProfitabilitySection+TypeHandle __TypeHandle;

    protected System.String group { protected get; }
    private Game.UI.InGame.CompanyProfitability profitability { private get; private set; }
    private Unity.Collections.NativeList<Game.UI.InGame.FactorInfo> profitabilityFactors { private get; private set; }

    public ProfitabilitySection();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
}
```


## Fields

- `private Game.Simulation.TaxSystem m_TaxSystem`  

```csharp
private Game.Simulation.TaxSystem m_TaxSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Unity.Entities.EntityQuery m_DistrictBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_DistrictBuildingQuery;
```

- `private Unity.Entities.EntityQuery m_ProcessQuery`  

```csharp
private Unity.Entities.EntityQuery m_ProcessQuery;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `public Unity.Collections.NativeArray<System.Int32> m_Results`  

```csharp
public Unity.Collections.NativeArray<System.Int32> m_Results;
```

- `private Game.UI.InGame.CompanyProfitability <profitability>k__BackingField`  

```csharp
private Game.UI.InGame.CompanyProfitability <profitability>k__BackingField;
```

- `private Unity.Collections.NativeArray<Unity.Mathematics.int2> m_Factors`  

```csharp
private Unity.Collections.NativeArray<Unity.Mathematics.int2> m_Factors;
```

- `private Unity.Collections.NativeList<Game.UI.InGame.FactorInfo> <profitabilityFactors>k__BackingField`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.FactorInfo> <profitabilityFactors>k__BackingField;
```

- `private Game.UI.InGame.ProfitabilitySection+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.ProfitabilitySection+TypeHandle __TypeHandle;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private Game.UI.InGame.CompanyProfitability profitability { private get; private set }`  

```csharp
private Game.UI.InGame.CompanyProfitability profitability { private get; private set; }
```

- `private Unity.Collections.NativeList<Game.UI.InGame.FactorInfo> profitabilityFactors { private get; private set }`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.FactorInfo> profitabilityFactors { private get; private set; }
```


## Constructors

- `public ProfitabilitySection()`  

```csharp
public ProfitabilitySection();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected virtual System.Void OnProcess();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
```

- `protected virtual Reset() : System.Void`  

```csharp
protected virtual System.Void Reset();
```


## Nested types

- `Game.UI.InGame.ProfitabilitySection+Result`  
- `Game.UI.InGame.ProfitabilitySection+ProfitabilityJob`  
- `Game.UI.InGame.ProfitabilitySection+DistrictProfitabilityJob`  
- `Game.UI.InGame.ProfitabilitySection+TypeHandle`  

