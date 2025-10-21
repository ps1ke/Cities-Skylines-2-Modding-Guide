# Game.Serialization.ResetUpdateGroupSizesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ResetUpdateGroupSizesSystem : Game.GameSystemBase
{
    private Game.Simulation.UpdateGroupSystem m_UpdateGroupSystem;
    private Game.Simulation.UpdateGroupSystem+UpdateGroupTypes m_UpdateGroupTypes;
    private Unity.Entities.EntityQuery m_UpdateFrameQuery;
    private Game.Serialization.ResetUpdateGroupSizesSystem+TypeHandle __TypeHandle;

    public ResetUpdateGroupSizesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.UpdateGroupSystem m_UpdateGroupSystem`  

```csharp
private Game.Simulation.UpdateGroupSystem m_UpdateGroupSystem;
```

- `private Game.Simulation.UpdateGroupSystem+UpdateGroupTypes m_UpdateGroupTypes`  

```csharp
private Game.Simulation.UpdateGroupSystem+UpdateGroupTypes m_UpdateGroupTypes;
```

- `private Unity.Entities.EntityQuery m_UpdateFrameQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdateFrameQuery;
```

- `private Game.Serialization.ResetUpdateGroupSizesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.ResetUpdateGroupSizesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ResetUpdateGroupSizesSystem()`  

```csharp
public ResetUpdateGroupSizesSystem();
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

- `Game.Serialization.ResetUpdateGroupSizesSystem+ResetUpdateGroupSizesJob`  
- `Game.Serialization.ResetUpdateGroupSizesSystem+TypeHandle`  

