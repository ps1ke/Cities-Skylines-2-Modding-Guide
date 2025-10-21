# Game.Rendering.EventInterpolateSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class EventInterpolateSystem : Game.GameSystemBase
{
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Unity.Entities.EntityQuery m_EventQuery;
    private Game.Rendering.EventInterpolateSystem+TypeHandle __TypeHandle;

    public EventInterpolateSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Unity.Entities.EntityQuery m_EventQuery`  

```csharp
private Unity.Entities.EntityQuery m_EventQuery;
```

- `private Game.Rendering.EventInterpolateSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.EventInterpolateSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public EventInterpolateSystem()`  

```csharp
public EventInterpolateSystem();
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

- `Game.Rendering.EventInterpolateSystem+UpdateTransformDataJob`  
- `Game.Rendering.EventInterpolateSystem+TypeHandle`  

