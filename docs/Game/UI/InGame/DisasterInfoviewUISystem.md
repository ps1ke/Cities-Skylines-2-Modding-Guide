# Game.UI.InGame.DisasterInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DisasterInfoviewUISystem : Game.UI.InGame.InfoviewUISystemBase, Game.Serialization.IPreDeserialize
{
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_ShelteredCount;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_ShelterCapacity;
    private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_ShelterAvailability;
    private Colossal.Collections.NativeAccumulator<Game.UI.InGame.DisasterInfoviewUISystem+UpdateDisasterResponseJob+Result> m_Result;
    private Unity.Entities.EntityQuery m_SheltersQuery;
    private Unity.Entities.EntityQuery m_SheltersModifiedQuery;
    private Game.UI.InGame.DisasterInfoviewUISystem+TypeHandle __TypeHandle;
    private static const System.String kGroup;

    protected System.Boolean Active { protected get; }
    protected System.Boolean Modified { protected get; }

    public DisasterInfoviewUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void PerformUpdate();
}
```


## Fields

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_ShelteredCount`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_ShelteredCount;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_ShelterCapacity`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_ShelterCapacity;
```

- `private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_ShelterAvailability`  

```csharp
private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_ShelterAvailability;
```

- `private Colossal.Collections.NativeAccumulator<Game.UI.InGame.DisasterInfoviewUISystem+UpdateDisasterResponseJob+Result> m_Result`  

```csharp
private Colossal.Collections.NativeAccumulator<Game.UI.InGame.DisasterInfoviewUISystem+UpdateDisasterResponseJob+Result> m_Result;
```

- `private Unity.Entities.EntityQuery m_SheltersQuery`  

```csharp
private Unity.Entities.EntityQuery m_SheltersQuery;
```

- `private Unity.Entities.EntityQuery m_SheltersModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_SheltersModifiedQuery;
```

- `private Game.UI.InGame.DisasterInfoviewUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.DisasterInfoviewUISystem+TypeHandle __TypeHandle;
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

- `public DisasterInfoviewUISystem()`  

```csharp
public DisasterInfoviewUISystem();
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

- `Game.UI.InGame.DisasterInfoviewUISystem+UpdateDisasterResponseJob`  
- `Game.UI.InGame.DisasterInfoviewUISystem+TypeHandle`  

