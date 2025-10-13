# Game.UI.InGame.TrafficInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TrafficInfoviewUISystem : Game.UI.InGame.InfoviewUISystemBase, Game.Serialization.IPreDeserialize
{
    private Unity.Entities.EntityQuery m_AggregateQuery;
    private Colossal.UI.Binding.RawValueBinding m_TrafficFlow;
    private Unity.Collections.NativeArray<System.Single> m_Results;
    private System.Single[] m_Flow;
    private Game.UI.InGame.TrafficInfoviewUISystem+TypeHandle __TypeHandle;
    private static const System.String kGroup;

    protected System.Boolean Active { protected get; }

    public TrafficInfoviewUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void PerformUpdate();
    private System.Void Reset();
    private System.Void UpdateTrafficFlowBinding(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_AggregateQuery`  

```csharp
private Unity.Entities.EntityQuery m_AggregateQuery;
```

- `private Colossal.UI.Binding.RawValueBinding m_TrafficFlow`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_TrafficFlow;
```

- `private Unity.Collections.NativeArray<System.Single> m_Results`  

```csharp
private Unity.Collections.NativeArray<System.Single> m_Results;
```

- `private System.Single[] m_Flow`  

```csharp
private System.Single[] m_Flow;
```

- `private Game.UI.InGame.TrafficInfoviewUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.TrafficInfoviewUISystem+TypeHandle __TypeHandle;
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

- `public TrafficInfoviewUISystem()`  

```csharp
public TrafficInfoviewUISystem();
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

- `private Reset() : System.Void`  

```csharp
private System.Void Reset();
```

- `private UpdateTrafficFlowBinding(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void UpdateTrafficFlowBinding(Colossal.UI.Binding.IJsonWriter writer);
```


## Nested types

- `Game.UI.InGame.TrafficInfoviewUISystem+UpdateFlowJob`  
- `Game.UI.InGame.TrafficInfoviewUISystem+TypeHandle`  

