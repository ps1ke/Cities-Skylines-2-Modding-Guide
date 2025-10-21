# Game.Net.TrafficLightInitializationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TrafficLightInitializationSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_TrafficLightsQuery;
    private Game.Net.TrafficLightInitializationSystem+TypeHandle __TypeHandle;

    public TrafficLightInitializationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_TrafficLightsQuery`  

```csharp
private Unity.Entities.EntityQuery m_TrafficLightsQuery;
```

- `private Game.Net.TrafficLightInitializationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Net.TrafficLightInitializationSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TrafficLightInitializationSystem()`  

```csharp
public TrafficLightInitializationSystem();
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

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Net.TrafficLightInitializationSystem+LaneGroup`  
- `Game.Net.TrafficLightInitializationSystem+InitializeTrafficLightsJob`  
- `Game.Net.TrafficLightInitializationSystem+TypeHandle`  

