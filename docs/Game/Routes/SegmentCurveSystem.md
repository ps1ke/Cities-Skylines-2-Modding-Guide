# Game.Routes.SegmentCurveSystem

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SegmentCurveSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_UpdatedRoutesQuery;
    private Unity.Entities.EntityQuery m_AllRoutesQuery;
    private System.Boolean m_Loaded;
    private Game.Routes.SegmentCurveSystem+TypeHandle __TypeHandle;

    public SegmentCurveSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Boolean GetLoaded();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_UpdatedRoutesQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedRoutesQuery;
```

- `private Unity.Entities.EntityQuery m_AllRoutesQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllRoutesQuery;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Routes.SegmentCurveSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Routes.SegmentCurveSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public SegmentCurveSystem()`  

```csharp
public SegmentCurveSystem();
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

- `Game.Routes.SegmentCurveSystem+FindUpdatedSegmentsJob`  
- `Game.Routes.SegmentCurveSystem+UpdateSegmentCurvesJob`  
- `Game.Routes.SegmentCurveSystem+TypeHandle`  

