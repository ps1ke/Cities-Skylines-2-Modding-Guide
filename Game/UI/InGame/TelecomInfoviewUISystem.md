# Game.UI.InGame.TelecomInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

## Code

```csharp
public class TelecomInfoviewUISystem : Game.UI.InGame.InfoviewUISystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Unity.Entities.EntityQuery m_TelecomQuery;
    private Unity.Entities.EntityQuery m_TelecomModifiedQuery;
    private Unity.Entities.EntityQuery m_DensityQuery;
    private Unity.Collections.NativeArray<Game.Simulation.TelecomCoverage> m_Coverage;
    private Unity.Collections.NativeArray<Game.Simulation.TelecomStatus> m_Status;
    private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_NetworkAvailability;
    private static const System.String kGroup;

    protected System.Boolean Active { protected get; }
    protected System.Boolean Modified { protected get; }

    public TelecomInfoviewUISystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void PerformUpdate();
}
```


## Fields

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Unity.Entities.EntityQuery m_TelecomQuery`  

```csharp
private Unity.Entities.EntityQuery m_TelecomQuery;
```

- `private Unity.Entities.EntityQuery m_TelecomModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_TelecomModifiedQuery;
```

- `private Unity.Entities.EntityQuery m_DensityQuery`  

```csharp
private Unity.Entities.EntityQuery m_DensityQuery;
```

- `private Unity.Collections.NativeArray<Game.Simulation.TelecomCoverage> m_Coverage`  

```csharp
private Unity.Collections.NativeArray<Game.Simulation.TelecomCoverage> m_Coverage;
```

- `private Unity.Collections.NativeArray<Game.Simulation.TelecomStatus> m_Status`  

```csharp
private Unity.Collections.NativeArray<Game.Simulation.TelecomStatus> m_Status;
```

- `private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_NetworkAvailability`  

```csharp
private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_NetworkAvailability;
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

- `public TelecomInfoviewUISystem()`  

```csharp
public TelecomInfoviewUISystem();
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual PerformUpdate() : System.Void`  

```csharp
protected virtual System.Void PerformUpdate();
```


