# Game.Prefabs.AreaInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AreaInitializeSystem : Game.GameSystemBase
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private Unity.Entities.EntityQuery m_SubAreaQuery;
    private Unity.Entities.EntityQuery m_PlaceholderQuery;
    private Game.Prefabs.AreaInitializeSystem+TypeHandle __TypeHandle;

    public AreaInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void InitializeAreaPrefabs();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    private System.Void ValidateSubAreas();
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Unity.Entities.EntityQuery m_PrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabQuery;
```

- `private Unity.Entities.EntityQuery m_SubAreaQuery`  

```csharp
private Unity.Entities.EntityQuery m_SubAreaQuery;
```

- `private Unity.Entities.EntityQuery m_PlaceholderQuery`  

```csharp
private Unity.Entities.EntityQuery m_PlaceholderQuery;
```

- `private Game.Prefabs.AreaInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.AreaInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public AreaInitializeSystem()`  

```csharp
public AreaInitializeSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private InitializeAreaPrefabs() : System.Void`  

```csharp
private System.Void InitializeAreaPrefabs();
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

- `private ValidateSubAreas() : System.Void`  

```csharp
private System.Void ValidateSubAreas();
```


## Nested types

- `Game.Prefabs.AreaInitializeSystem+FixPlaceholdersJob`  
- `Game.Prefabs.AreaInitializeSystem+ValidateSubAreasJob`  
- `Game.Prefabs.AreaInitializeSystem+TypeHandle`  

