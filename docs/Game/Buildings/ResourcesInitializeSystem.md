# Game.Buildings.ResourcesInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ResourcesInitializeSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_Additions;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Buildings.ResourcesInitializeSystem+TypeHandle __TypeHandle;

    public ResourcesInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_Additions`  

```csharp
private Unity.Entities.EntityQuery m_Additions;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Buildings.ResourcesInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Buildings.ResourcesInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ResourcesInitializeSystem()`  

```csharp
public ResourcesInitializeSystem();
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

- `Game.Buildings.ResourcesInitializeSystem+InitializeCityServiceJob`  
- `Game.Buildings.ResourcesInitializeSystem+TypeHandle`  

