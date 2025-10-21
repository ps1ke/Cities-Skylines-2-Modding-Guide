# Game.UI.InGame.PostInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PostInfoviewUISystem : Game.UI.InGame.InfoviewUISystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Unity.Entities.EntityQuery m_PostFacilityModifiedQuery;
    private Unity.Entities.EntityQuery m_MailProducerQuery;
    private Unity.Entities.EntityQuery m_MailProducerModifiedQuery;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_CollectedMail;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_DeliveredMail;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_MailProductionRate;
    private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_PostServiceAvailability;
    private Unity.Collections.NativeArray<Unity.Mathematics.float2> m_Result;
    private Game.UI.InGame.PostInfoviewUISystem+TypeHandle __TypeHandle;
    private static const System.String kGroup;
    private static const System.Single kAccumulationFactor;

    protected System.Boolean Active { protected get; }
    protected System.Boolean Modified { protected get; }

    public PostInfoviewUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void PerformUpdate();
    private System.Void ResetResults();
    private System.Void UpdateAvailability();
    private System.Void UpdateMailRate();
    private System.Void UpdateProcessingRate();
}
```


## Fields

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Unity.Entities.EntityQuery m_PostFacilityModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_PostFacilityModifiedQuery;
```

- `private Unity.Entities.EntityQuery m_MailProducerQuery`  

```csharp
private Unity.Entities.EntityQuery m_MailProducerQuery;
```

- `private Unity.Entities.EntityQuery m_MailProducerModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_MailProducerModifiedQuery;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_CollectedMail`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_CollectedMail;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_DeliveredMail`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_DeliveredMail;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_MailProductionRate`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_MailProductionRate;
```

- `private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_PostServiceAvailability`  

```csharp
private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_PostServiceAvailability;
```

- `private Unity.Collections.NativeArray<Unity.Mathematics.float2> m_Result`  

```csharp
private Unity.Collections.NativeArray<Unity.Mathematics.float2> m_Result;
```

- `private Game.UI.InGame.PostInfoviewUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.PostInfoviewUISystem+TypeHandle __TypeHandle;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```

- `private static const System.Single kAccumulationFactor`  

```csharp
private static const System.Single kAccumulationFactor;
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

- `public PostInfoviewUISystem()`  

```csharp
public PostInfoviewUISystem();
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

- `private ResetResults() : System.Void`  

```csharp
private System.Void ResetResults();
```

- `private UpdateAvailability() : System.Void`  

```csharp
private System.Void UpdateAvailability();
```

- `private UpdateMailRate() : System.Void`  

```csharp
private System.Void UpdateMailRate();
```

- `private UpdateProcessingRate() : System.Void`  

```csharp
private System.Void UpdateProcessingRate();
```


## Nested types

- `Game.UI.InGame.PostInfoviewUISystem+UpdateMailRateJob`  
- `Game.UI.InGame.PostInfoviewUISystem+TypeHandle`  

