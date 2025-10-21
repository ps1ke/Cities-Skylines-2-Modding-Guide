# Game.Areas.AreaConnectionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AreaConnectionSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier4B m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_ModificationQuery;
    private Unity.Entities.EntityQuery m_ConnectionQuery;
    private Unity.Entities.ComponentTypeSet m_AppliedTypes;
    private Game.Areas.AreaConnectionSystem+TypeHandle __TypeHandle;

    public AreaConnectionSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier4B m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier4B m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_ModificationQuery`  

```csharp
private Unity.Entities.EntityQuery m_ModificationQuery;
```

- `private Unity.Entities.EntityQuery m_ConnectionQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConnectionQuery;
```

- `private Unity.Entities.ComponentTypeSet m_AppliedTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_AppliedTypes;
```

- `private Game.Areas.AreaConnectionSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Areas.AreaConnectionSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public AreaConnectionSystem()`  

```csharp
public AreaConnectionSystem();
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

- `Game.Areas.AreaConnectionSystem+LaneType`  
- `Game.Areas.AreaConnectionSystem+AreaLaneKey`  
- `Game.Areas.AreaConnectionSystem+AreaLaneValue`  
- `Game.Areas.AreaConnectionSystem+TriangleSideKey`  
- `Game.Areas.AreaConnectionSystem+UpdateSecondaryLanesJob`  
- `Game.Areas.AreaConnectionSystem+TypeHandle`  

