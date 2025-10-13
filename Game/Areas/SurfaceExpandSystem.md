# Game.Areas.SurfaceExpandSystem

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SurfaceExpandSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_UpdatedAreasQuery;
    private Unity.Entities.EntityQuery m_AllAreasQuery;
    private System.Boolean m_Loaded;
    private Game.Areas.SurfaceExpandSystem+TypeHandle __TypeHandle;

    public SurfaceExpandSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Boolean GetLoaded();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_UpdatedAreasQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedAreasQuery;
```

- `private Unity.Entities.EntityQuery m_AllAreasQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllAreasQuery;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Areas.SurfaceExpandSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Areas.SurfaceExpandSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public SurfaceExpandSystem()`  

```csharp
public SurfaceExpandSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private GetLoaded() : System.Boolean`  

```csharp
private System.Boolean GetLoaded();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Areas.SurfaceExpandSystem+ExpandAreasJob`  
- `Game.Areas.SurfaceExpandSystem+TypeHandle`  

