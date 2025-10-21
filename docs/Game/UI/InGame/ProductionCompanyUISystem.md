# Game.UI.InGame.ProductionCompanyUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ProductionCompanyUISystem : Game.UI.UISystemBase
{
    private Game.Simulation.IBudgetSystem m_BudgetSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private System.Collections.Generic.Dictionary<System.String, Game.Economy.Resource> m_ResourceIDMap;
    private Colossal.UI.Binding.RawValueBinding m_ProductionCompanyInfoBinding;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_IndustrialCompanyWealthBinding;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_CommercialCompanyWealthBinding;
    private Unity.Collections.NativeArray<Game.UI.InGame.ProductionCompanyUISystem+ProductionLevelInfo> m_CachedValues;
    private Unity.Collections.NativeArray<Game.UI.InGame.ProductionCompanyUISystem+ProductionLevelInfo> m_Values;
    private Game.Economy.Resource m_SelectedResource;
    private Unity.Collections.NativeQueue<Game.UI.InGame.ProductionCompanyUISystem+ProductionCompanyInfo> m_ProductionCompanyInfoQueue;
    private Unity.Entities.EntityQuery m_CompanyQuery;
    private Game.UI.InGame.ProductionCompanyUISystem+TypeHandle __TypeHandle;
    private static readonly System.String kGroup;
    private static readonly System.Int32 kLevels;

    public ProductionCompanyUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    private System.Void OnSelectResource(System.String resourceID);
    protected virtual System.Void OnUpdate();
    private System.Void Patch(System.Int32 index, System.String fieldName, System.Int32 value);
    private System.Void PatchProductionCompanyInfo();
    private System.Void RebuildResourceIDMap();
    private System.Void UpdateProductionCompanyInfo(Colossal.UI.Binding.IJsonWriter binder);
}
```


## Fields

- `private Game.Simulation.IBudgetSystem m_BudgetSystem`  

```csharp
private Game.Simulation.IBudgetSystem m_BudgetSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private System.Collections.Generic.Dictionary<System.String, Game.Economy.Resource> m_ResourceIDMap`  

```csharp
private System.Collections.Generic.Dictionary<System.String, Game.Economy.Resource> m_ResourceIDMap;
```

- `private Colossal.UI.Binding.RawValueBinding m_ProductionCompanyInfoBinding`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_ProductionCompanyInfoBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_IndustrialCompanyWealthBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_IndustrialCompanyWealthBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_CommercialCompanyWealthBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_CommercialCompanyWealthBinding;
```

- `private Unity.Collections.NativeArray<Game.UI.InGame.ProductionCompanyUISystem+ProductionLevelInfo> m_CachedValues`  

```csharp
private Unity.Collections.NativeArray<Game.UI.InGame.ProductionCompanyUISystem+ProductionLevelInfo> m_CachedValues;
```

- `private Unity.Collections.NativeArray<Game.UI.InGame.ProductionCompanyUISystem+ProductionLevelInfo> m_Values`  

```csharp
private Unity.Collections.NativeArray<Game.UI.InGame.ProductionCompanyUISystem+ProductionLevelInfo> m_Values;
```

- `private Game.Economy.Resource m_SelectedResource`  

```csharp
private Game.Economy.Resource m_SelectedResource;
```

- `private Unity.Collections.NativeQueue<Game.UI.InGame.ProductionCompanyUISystem+ProductionCompanyInfo> m_ProductionCompanyInfoQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.UI.InGame.ProductionCompanyUISystem+ProductionCompanyInfo> m_ProductionCompanyInfoQueue;
```

- `private Unity.Entities.EntityQuery m_CompanyQuery`  

```csharp
private Unity.Entities.EntityQuery m_CompanyQuery;
```

- `private Game.UI.InGame.ProductionCompanyUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.ProductionCompanyUISystem+TypeHandle __TypeHandle;
```

- `private static readonly System.String kGroup`  

```csharp
private static readonly System.String kGroup;
```

- `private static readonly System.Int32 kLevels`  

```csharp
private static readonly System.Int32 kLevels;
```


## Constructors

- `public ProductionCompanyUISystem()`  

```csharp
public ProductionCompanyUISystem();
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

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `private OnSelectResource(System.String resourceID) : System.Void`  

```csharp
private System.Void OnSelectResource(System.String resourceID);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private Patch(System.Int32 index, System.String fieldName, System.Int32 value) : System.Void`  

```csharp
private System.Void Patch(System.Int32 index, System.String fieldName, System.Int32 value);
```

- `private PatchProductionCompanyInfo() : System.Void`  

```csharp
private System.Void PatchProductionCompanyInfo();
```

- `private RebuildResourceIDMap() : System.Void`  

```csharp
private System.Void RebuildResourceIDMap();
```

- `private UpdateProductionCompanyInfo(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private System.Void UpdateProductionCompanyInfo(Colossal.UI.Binding.IJsonWriter binder);
```


## Nested types

- `Game.UI.InGame.ProductionCompanyUISystem+MapCompanyStatisticsJob`  
- `Game.UI.InGame.ProductionCompanyUISystem+ProductionCompanyInfo`  
- `Game.UI.InGame.ProductionCompanyUISystem+ProductionLevelInfo`  
- `Game.UI.InGame.ProductionCompanyUISystem+TypeHandle`  

