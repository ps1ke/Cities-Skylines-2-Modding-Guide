# Game.Objects.QuantityUpdateSystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class QuantityUpdateSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_QuantityQuery;
    private Unity.Entities.EntityQuery m_PostConfigurationQuery;
    private Unity.Entities.EntityQuery m_GarbageConfigurationQuery;
    private Game.Objects.QuantityUpdateSystem+TypeHandle __TypeHandle;

    public QuantityUpdateSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_QuantityQuery`  

```csharp
private Unity.Entities.EntityQuery m_QuantityQuery;
```

- `private Unity.Entities.EntityQuery m_PostConfigurationQuery`  

```csharp
private Unity.Entities.EntityQuery m_PostConfigurationQuery;
```

- `private Unity.Entities.EntityQuery m_GarbageConfigurationQuery`  

```csharp
private Unity.Entities.EntityQuery m_GarbageConfigurationQuery;
```

- `private Game.Objects.QuantityUpdateSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Objects.QuantityUpdateSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public QuantityUpdateSystem()`  

```csharp
public QuantityUpdateSystem();
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

- `Game.Objects.QuantityUpdateSystem+UpdateQuantityJob`  
- `Game.Objects.QuantityUpdateSystem+TypeHandle`  

