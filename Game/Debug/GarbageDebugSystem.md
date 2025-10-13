# Game.Debug.GarbageDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GarbageDebugSystem : Game.Debug.BaseDebugSystem
{
    private Unity.Entities.EntityQuery m_BuildingGroup;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Debug.BaseDebugSystem+Option m_AccumulatedOption;
    private Game.Debug.BaseDebugSystem+Option m_ProduceOption;
    private Game.Debug.GarbageDebugSystem+TypeHandle __TypeHandle;

    public GarbageDebugSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_BuildingGroup`  

```csharp
private Unity.Entities.EntityQuery m_BuildingGroup;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Debug.BaseDebugSystem+Option m_AccumulatedOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_AccumulatedOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_ProduceOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_ProduceOption;
```

- `private Game.Debug.GarbageDebugSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Debug.GarbageDebugSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public GarbageDebugSystem()`  

```csharp
public GarbageDebugSystem();
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

- `Game.Debug.GarbageDebugSystem+GarbageGizmoJob`  
- `Game.Debug.GarbageDebugSystem+TypeHandle`  

