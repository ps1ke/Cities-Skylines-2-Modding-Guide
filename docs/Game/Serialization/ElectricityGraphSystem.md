# Game.Serialization.ElectricityGraphSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ElectricityGraphSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_NetEdgeQuery;
    private Unity.Entities.EntityQuery m_BuildingQuery;
    private Game.Serialization.ElectricityGraphSystem+TypeHandle __TypeHandle;

    public ElectricityGraphSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_NetEdgeQuery`  

```csharp
private Unity.Entities.EntityQuery m_NetEdgeQuery;
```

- `private Unity.Entities.EntityQuery m_BuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingQuery;
```

- `private Game.Serialization.ElectricityGraphSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.ElectricityGraphSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ElectricityGraphSystem()`  

```csharp
public ElectricityGraphSystem();
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

- `Game.Serialization.ElectricityGraphSystem+EdgeJob`  
- `Game.Serialization.ElectricityGraphSystem+BuildingJob`  
- `Game.Serialization.ElectricityGraphSystem+TypeHandle`  

