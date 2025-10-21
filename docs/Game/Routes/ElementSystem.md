# Game.Routes.ElementSystem

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ElementSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_RouteQuery;
    private Game.Common.ModificationBarrier2B m_ModificationBarrier;
    private Game.Routes.ElementSystem+TypeHandle __TypeHandle;

    public ElementSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_RouteQuery`  

```csharp
private Unity.Entities.EntityQuery m_RouteQuery;
```

- `private Game.Common.ModificationBarrier2B m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier2B m_ModificationBarrier;
```

- `private Game.Routes.ElementSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Routes.ElementSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ElementSystem()`  

```csharp
public ElementSystem();
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

- `Game.Routes.ElementSystem+CheckRouteElementsJob`  
- `Game.Routes.ElementSystem+TypeHandle`  

