# Game.Zones.BlockSystem

**Assembly:** `Game`  
**Namespace:** `Game.Zones`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BlockSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_UpdatedEdgesQuery;
    private Game.Common.ModificationBarrier4 m_ModificationBarrier;
    private Game.Zones.BlockSystem+TypeHandle __TypeHandle;

    public BlockSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_UpdatedEdgesQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedEdgesQuery;
```

- `private Game.Common.ModificationBarrier4 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier4 m_ModificationBarrier;
```

- `private Game.Zones.BlockSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Zones.BlockSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public BlockSystem()`  

```csharp
public BlockSystem();
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

- `Game.Zones.BlockSystem+UpdateBlocksJob`  
- `Game.Zones.BlockSystem+TypeHandle`  

