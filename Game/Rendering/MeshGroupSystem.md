# Game.Rendering.MeshGroupSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class MeshGroupSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_UpdateQuery;
    private Unity.Entities.EntityQuery m_AllQuery;
    private System.Boolean m_Loaded;
    private Game.Rendering.MeshGroupSystem+TypeHandle __TypeHandle;

    public MeshGroupSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Boolean GetLoaded();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_UpdateQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdateQuery;
```

- `private Unity.Entities.EntityQuery m_AllQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllQuery;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Rendering.MeshGroupSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.MeshGroupSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public MeshGroupSystem()`  

```csharp
public MeshGroupSystem();
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

- `Game.Rendering.MeshGroupSystem+SetMeshGroupsJob`  
- `Game.Rendering.MeshGroupSystem+TypeHandle`  

