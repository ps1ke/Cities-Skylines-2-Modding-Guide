# Game.Prefabs.NetCompositionMeshRefSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NetCompositionMeshRefSystem : Game.GameSystemBase
{
    private Game.Prefabs.NetCompositionMeshSystem m_NetCompositionMeshSystem;
    private Game.Common.ModificationBarrier4 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_CompositionQuery;
    private Unity.Entities.EntityArchetype m_MeshArchetype;
    private Game.Prefabs.NetCompositionMeshRefSystem+TypeHandle __TypeHandle;

    public NetCompositionMeshRefSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Prefabs.NetCompositionMeshSystem m_NetCompositionMeshSystem`  

```csharp
private Game.Prefabs.NetCompositionMeshSystem m_NetCompositionMeshSystem;
```

- `private Game.Common.ModificationBarrier4 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier4 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_CompositionQuery`  

```csharp
private Unity.Entities.EntityQuery m_CompositionQuery;
```

- `private Unity.Entities.EntityArchetype m_MeshArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_MeshArchetype;
```

- `private Game.Prefabs.NetCompositionMeshRefSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.NetCompositionMeshRefSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public NetCompositionMeshRefSystem()`  

```csharp
public NetCompositionMeshRefSystem();
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

- `Game.Prefabs.NetCompositionMeshRefSystem+NewMeshData`  
- `Game.Prefabs.NetCompositionMeshRefSystem+CompositionMeshRefJob`  
- `Game.Prefabs.NetCompositionMeshRefSystem+TypeHandle`  

