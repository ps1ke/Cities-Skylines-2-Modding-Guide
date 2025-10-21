# Game.Prefabs.ZonePrefabInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ZonePrefabInitializeSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_PrefabGroup;
    private Unity.Entities.EntityQuery m_ProcessGroup;
    private Unity.Entities.EntityQuery m_EconomyParameterGroup;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Prefabs.ZonePrefabInitializeSystem+TypeHandle __TypeHandle;

    public ZonePrefabInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_PrefabGroup`  

```csharp
private Unity.Entities.EntityQuery m_PrefabGroup;
```

- `private Unity.Entities.EntityQuery m_ProcessGroup`  

```csharp
private Unity.Entities.EntityQuery m_ProcessGroup;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterGroup`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterGroup;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Prefabs.ZonePrefabInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.ZonePrefabInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ZonePrefabInitializeSystem()`  

```csharp
public ZonePrefabInitializeSystem();
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

- `Game.Prefabs.ZonePrefabInitializeSystem+TypeHandle`  

