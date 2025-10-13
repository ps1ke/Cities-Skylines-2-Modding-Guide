# Game.Net.FlipTrafficHandednessSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class FlipTrafficHandednessSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_RoadEdgeQuery;
    private Game.Net.FlipTrafficHandednessSystem+TypeHandle __TypeHandle;

    public FlipTrafficHandednessSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_RoadEdgeQuery`  

```csharp
private Unity.Entities.EntityQuery m_RoadEdgeQuery;
```

- `private Game.Net.FlipTrafficHandednessSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Net.FlipTrafficHandednessSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public FlipTrafficHandednessSystem()`  

```csharp
public FlipTrafficHandednessSystem();
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

- `Game.Net.FlipTrafficHandednessSystem+FlipOnewayRoadsJob`  
- `Game.Net.FlipTrafficHandednessSystem+TypeHandle`  

