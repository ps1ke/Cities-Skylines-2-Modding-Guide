# Game.Prefabs.UIInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class UIInitializeSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Entities.EntityQuery m_PolicyQuery;
    private Game.Prefabs.UIInitializeSystem+TypeHandle __TypeHandle;

    public System.Collections.Generic.IEnumerable<Game.Prefabs.PolicyPrefab> policies { get; }

    public UIInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    private System.Void RemoveFrom(Unity.Entities.Entity entity, Unity.Entities.DynamicBuffer<Game.Prefabs.UIGroupElement> uiGroupElements);
    private System.Void RemoveFrom(Unity.Entities.Entity entity, Unity.Entities.DynamicBuffer<Game.Prefabs.UnlockRequirement> unlockRequirements);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_PrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabQuery;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Unity.Entities.EntityQuery m_PolicyQuery`  

```csharp
private Unity.Entities.EntityQuery m_PolicyQuery;
```

- `private Game.Prefabs.UIInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.UIInitializeSystem+TypeHandle __TypeHandle;
```


## Properties

- `public System.Collections.Generic.IEnumerable<Game.Prefabs.PolicyPrefab> policies { get }`  

```csharp
public System.Collections.Generic.IEnumerable<Game.Prefabs.PolicyPrefab> policies { get; }
```


## Constructors

- `public UIInitializeSystem()`  

```csharp
public UIInitializeSystem();
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

- `private RemoveFrom(Unity.Entities.Entity entity, Unity.Entities.DynamicBuffer<Game.Prefabs.UIGroupElement> uiGroupElements) : System.Void`  

```csharp
private System.Void RemoveFrom(Unity.Entities.Entity entity, Unity.Entities.DynamicBuffer<Game.Prefabs.UIGroupElement> uiGroupElements);
```

- `private RemoveFrom(Unity.Entities.Entity entity, Unity.Entities.DynamicBuffer<Game.Prefabs.UnlockRequirement> unlockRequirements) : System.Void`  

```csharp
private System.Void RemoveFrom(Unity.Entities.Entity entity, Unity.Entities.DynamicBuffer<Game.Prefabs.UnlockRequirement> unlockRequirements);
```


## Nested types

- `Game.Prefabs.UIInitializeSystem+TypeHandle`  
- `Game.Prefabs.UIInitializeSystem+<get_policies>d__4`  

