# Game.Objects.ContainerClearSystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ContainerClearSystem : Game.GameSystemBase
{
    private Game.Serialization.LoadGameSystem m_LoadGameSystem;
    private Unity.Entities.EntityQuery m_EntityQuery;
    private Unity.Entities.ComponentTypeSet m_SubTypes;
    private Game.Objects.ContainerClearSystem+TypeHandle __TypeHandle;

    public ContainerClearSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Serialization.LoadGameSystem m_LoadGameSystem`  

```csharp
private Game.Serialization.LoadGameSystem m_LoadGameSystem;
```

- `private Unity.Entities.EntityQuery m_EntityQuery`  

```csharp
private Unity.Entities.EntityQuery m_EntityQuery;
```

- `private Unity.Entities.ComponentTypeSet m_SubTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_SubTypes;
```

- `private Game.Objects.ContainerClearSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Objects.ContainerClearSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ContainerClearSystem()`  

```csharp
public ContainerClearSystem();
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

- `Game.Objects.ContainerClearSystem+ContainerClearJob`  
- `Game.Objects.ContainerClearSystem+TypeHandle`  

