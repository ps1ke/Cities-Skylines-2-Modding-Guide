# Game.UI.InGame.TransportInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

## Code

```csharp
public class TransportInfoviewUISystem : Game.UI.InGame.InfoviewUISystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Prefabs.UnlockSystem m_UnlockSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Unity.Entities.EntityQuery m_ConfigQuery;
    private Unity.Entities.EntityQuery m_LineQuery;
    private Unity.Entities.EntityQuery m_ModifiedLineQuery;
    private Colossal.UI.Binding.RawValueBinding m_Summaries;
    private Game.Prefabs.UITransportConfigurationPrefab m_Config;
    private static const System.String kGroup;

    protected System.Boolean Active { protected get; }
    protected System.Boolean Modified { protected get; }

    public TransportInfoviewUISystem();

    private System.Void BindSummaries(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void PerformUpdate();
}
```


## Fields

- `private Game.Prefabs.UnlockSystem m_UnlockSystem`  

```csharp
private Game.Prefabs.UnlockSystem m_UnlockSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.UI.InGame.PrefabUISystem m_PrefabUISystem`  

```csharp
private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
```

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Unity.Entities.EntityQuery m_ConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConfigQuery;
```

- `private Unity.Entities.EntityQuery m_LineQuery`  

```csharp
private Unity.Entities.EntityQuery m_LineQuery;
```

- `private Unity.Entities.EntityQuery m_ModifiedLineQuery`  

```csharp
private Unity.Entities.EntityQuery m_ModifiedLineQuery;
```

- `private Colossal.UI.Binding.RawValueBinding m_Summaries`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_Summaries;
```

- `private Game.Prefabs.UITransportConfigurationPrefab m_Config`  

```csharp
private Game.Prefabs.UITransportConfigurationPrefab m_Config;
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

- `protected System.Boolean Modified { protected get }`  

```csharp
protected System.Boolean Modified { protected get; }
```


## Constructors

- `public TransportInfoviewUISystem()`  

```csharp
public TransportInfoviewUISystem();
```


## Methods

- `private BindSummaries(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void BindSummaries(Colossal.UI.Binding.IJsonWriter writer);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual PerformUpdate() : System.Void`  

```csharp
protected virtual System.Void PerformUpdate();
```


## Nested types

- `Game.UI.InGame.TransportInfoviewUISystem+PassengerSummary`  
- `Game.UI.InGame.TransportInfoviewUISystem+CargoSummary`  

