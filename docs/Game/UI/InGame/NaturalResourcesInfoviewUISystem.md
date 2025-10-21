# Game.UI.InGame.NaturalResourcesInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NaturalResourcesInfoviewUISystem : Game.UI.InGame.InfoviewUISystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_AvailableOil;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_AvailableOre;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_AvailableForest;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_AvailableFertility;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_ForestRenewalRate;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_FertilityRenewalRate;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_FishRenewalRate;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_AvailableFish;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_OilExtractionRate;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_OreExtractionRate;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_ForestExtractionRate;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_FertilityExtractionRate;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_FishExtractionRate;
    private Unity.Entities.EntityQuery m_MapTileQuery;
    private Unity.Entities.EntityQuery m_ExtractorQuery;
    private Unity.Collections.NativeArray<System.Single> m_Results;
    private Game.UI.InGame.NaturalResourcesInfoviewUISystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_1701516005_0;
    private static const System.String kGroup;

    public Game.GameMode gameMode { get; }
    protected System.Boolean Active { protected get; }

    public NaturalResourcesInfoviewUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void PerformUpdate();
}
```


## Fields

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_AvailableOil`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_AvailableOil;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_AvailableOre`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_AvailableOre;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_AvailableForest`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_AvailableForest;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_AvailableFertility`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_AvailableFertility;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_ForestRenewalRate`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_ForestRenewalRate;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_FertilityRenewalRate`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_FertilityRenewalRate;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_FishRenewalRate`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_FishRenewalRate;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_AvailableFish`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_AvailableFish;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_OilExtractionRate`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_OilExtractionRate;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_OreExtractionRate`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_OreExtractionRate;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_ForestExtractionRate`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_ForestExtractionRate;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_FertilityExtractionRate`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_FertilityExtractionRate;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_FishExtractionRate`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_FishExtractionRate;
```

- `private Unity.Entities.EntityQuery m_MapTileQuery`  

```csharp
private Unity.Entities.EntityQuery m_MapTileQuery;
```

- `private Unity.Entities.EntityQuery m_ExtractorQuery`  

```csharp
private Unity.Entities.EntityQuery m_ExtractorQuery;
```

- `private Unity.Collections.NativeArray<System.Single> m_Results`  

```csharp
private Unity.Collections.NativeArray<System.Single> m_Results;
```

- `private Game.UI.InGame.NaturalResourcesInfoviewUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.NaturalResourcesInfoviewUISystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_1701516005_0`  

```csharp
private Unity.Entities.EntityQuery __query_1701516005_0;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Properties

- `public Game.GameMode gameMode { get }`  

```csharp
public Game.GameMode gameMode { get; }
```

- `protected System.Boolean Active { protected get }`  

```csharp
protected System.Boolean Active { protected get; }
```


## Constructors

- `public NaturalResourcesInfoviewUISystem()`  

```csharp
public NaturalResourcesInfoviewUISystem();
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

- `protected virtual PerformUpdate() : System.Void`  

```csharp
protected virtual System.Void PerformUpdate();
```


## Nested types

- `Game.UI.InGame.NaturalResourcesInfoviewUISystem+Result`  
- `Game.UI.InGame.NaturalResourcesInfoviewUISystem+UpdateResourcesJob`  
- `Game.UI.InGame.NaturalResourcesInfoviewUISystem+UpdateExtractionJob`  
- `Game.UI.InGame.NaturalResourcesInfoviewUISystem+TypeHandle`  

