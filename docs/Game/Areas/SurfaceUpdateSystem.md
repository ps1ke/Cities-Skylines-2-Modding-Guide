# Game.Areas.SurfaceUpdateSystem

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SurfaceUpdateSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Unity.Entities.EntityQuery m_UpdatedNetQuery;
    private Game.Areas.SurfaceUpdateSystem+TypeHandle __TypeHandle;

    public SurfaceUpdateSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_ModificationBarrier;
```

- `private Game.Areas.SearchSystem m_AreaSearchSystem`  

```csharp
private Game.Areas.SearchSystem m_AreaSearchSystem;
```

- `private Unity.Entities.EntityQuery m_UpdatedNetQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedNetQuery;
```

- `private Game.Areas.SurfaceUpdateSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Areas.SurfaceUpdateSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public SurfaceUpdateSystem()`  

```csharp
public SurfaceUpdateSystem();
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

- `Game.Areas.SurfaceUpdateSystem+UpdateAreasJob`  
- `Game.Areas.SurfaceUpdateSystem+TypeHandle`  

