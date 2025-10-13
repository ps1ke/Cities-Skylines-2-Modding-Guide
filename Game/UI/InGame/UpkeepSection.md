# Game.UI.InGame.UpkeepSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class UpkeepSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
    private Unity.Entities.EntityQuery m_BudgetDataQuery;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private System.Collections.Generic.Dictionary<System.String, Game.UI.InGame.UpkeepSection+UIUpkeepItem> <moneyUpkeep>k__BackingField;
    private System.Collections.Generic.Dictionary<Game.Economy.Resource, Game.UI.InGame.UpkeepSection+UIUpkeepItem> <resourceUpkeep>k__BackingField;
    private System.Collections.Generic.List<Game.UI.InGame.UpkeepSection+UIUpkeepItem> <upkeeps>k__BackingField;
    private System.Int32 <total>k__BackingField;
    private System.Boolean <inactive>k__BackingField;
    private Game.UI.InGame.UpkeepSection+TypeHandle __TypeHandle;

    protected System.String group { protected get; }
    private System.Collections.Generic.Dictionary<System.String, Game.UI.InGame.UpkeepSection+UIUpkeepItem> moneyUpkeep { private get; private set; }
    private System.Collections.Generic.Dictionary<Game.Economy.Resource, Game.UI.InGame.UpkeepSection+UIUpkeepItem> resourceUpkeep { private get; private set; }
    private System.Collections.Generic.List<Game.UI.InGame.UpkeepSection+UIUpkeepItem> upkeeps { private get; private set; }
    private System.Int32 total { private get; private set; }
    private System.Boolean inactive { private get; private set; }
    protected System.Boolean displayForUpgrades { protected get; }

    public UpkeepSection();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void CalculateServiceUpkeepDatas(Unity.Entities.Entity entity, Unity.Entities.Entity prefabEntity, Unity.Entities.Entity buildingOwnerEntity, Unity.Entities.DynamicBuffer<Game.Prefabs.ServiceUpkeepData> serviceUpkeepDatas, System.Boolean inactiveBuilding, System.Boolean inactiveUpgrade);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.UI.InGame.PrefabUISystem m_PrefabUISystem`  

```csharp
private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
```

- `private Unity.Entities.EntityQuery m_BudgetDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_BudgetDataQuery;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private System.Collections.Generic.Dictionary<System.String, Game.UI.InGame.UpkeepSection+UIUpkeepItem> <moneyUpkeep>k__BackingField`  

```csharp
private System.Collections.Generic.Dictionary<System.String, Game.UI.InGame.UpkeepSection+UIUpkeepItem> <moneyUpkeep>k__BackingField;
```

- `private System.Collections.Generic.Dictionary<Game.Economy.Resource, Game.UI.InGame.UpkeepSection+UIUpkeepItem> <resourceUpkeep>k__BackingField`  

```csharp
private System.Collections.Generic.Dictionary<Game.Economy.Resource, Game.UI.InGame.UpkeepSection+UIUpkeepItem> <resourceUpkeep>k__BackingField;
```

- `private System.Collections.Generic.List<Game.UI.InGame.UpkeepSection+UIUpkeepItem> <upkeeps>k__BackingField`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.UpkeepSection+UIUpkeepItem> <upkeeps>k__BackingField;
```

- `private System.Int32 <total>k__BackingField`  

```csharp
private System.Int32 <total>k__BackingField;
```

- `private System.Boolean <inactive>k__BackingField`  

```csharp
private System.Boolean <inactive>k__BackingField;
```

- `private Game.UI.InGame.UpkeepSection+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.UpkeepSection+TypeHandle __TypeHandle;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Collections.Generic.Dictionary<System.String, Game.UI.InGame.UpkeepSection+UIUpkeepItem> moneyUpkeep { private get; private set }`  

```csharp
private System.Collections.Generic.Dictionary<System.String, Game.UI.InGame.UpkeepSection+UIUpkeepItem> moneyUpkeep { private get; private set; }
```

- `private System.Collections.Generic.Dictionary<Game.Economy.Resource, Game.UI.InGame.UpkeepSection+UIUpkeepItem> resourceUpkeep { private get; private set }`  

```csharp
private System.Collections.Generic.Dictionary<Game.Economy.Resource, Game.UI.InGame.UpkeepSection+UIUpkeepItem> resourceUpkeep { private get; private set; }
```

- `private System.Collections.Generic.List<Game.UI.InGame.UpkeepSection+UIUpkeepItem> upkeeps { private get; private set }`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.UpkeepSection+UIUpkeepItem> upkeeps { private get; private set; }
```

- `private System.Int32 total { private get; private set }`  

```csharp
private System.Int32 total { private get; private set; }
```

- `private System.Boolean inactive { private get; private set }`  

```csharp
private System.Boolean inactive { private get; private set; }
```

- `protected System.Boolean displayForUpgrades { protected get }`  

```csharp
protected System.Boolean displayForUpgrades { protected get; }
```


## Constructors

- `public UpkeepSection()`  

```csharp
public UpkeepSection();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private CalculateServiceUpkeepDatas(Unity.Entities.Entity entity, Unity.Entities.Entity prefabEntity, Unity.Entities.Entity buildingOwnerEntity, Unity.Entities.DynamicBuffer<Game.Prefabs.ServiceUpkeepData> serviceUpkeepDatas, System.Boolean inactiveBuilding, System.Boolean inactiveUpgrade) : System.Void`  

```csharp
private System.Void CalculateServiceUpkeepDatas(Unity.Entities.Entity entity, Unity.Entities.Entity prefabEntity, Unity.Entities.Entity buildingOwnerEntity, Unity.Entities.DynamicBuffer<Game.Prefabs.ServiceUpkeepData> serviceUpkeepDatas, System.Boolean inactiveBuilding, System.Boolean inactiveUpgrade);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
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

- `private Visible() : System.Boolean`  

```csharp
private System.Boolean Visible();
```


## Nested types

- `Game.UI.InGame.UpkeepSection+UIUpkeepItem`  
- `Game.UI.InGame.UpkeepSection+TypeHandle`  

