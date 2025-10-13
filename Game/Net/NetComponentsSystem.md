# Game.Net.NetComponentsSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NetComponentsSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier4 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_UpdatedNetQuery;
    private Unity.Entities.EntityQuery m_AllNetQuery;
    private System.Boolean m_Loaded;
    private Game.Net.NetComponentsSystem+TypeHandle __TypeHandle;

    public NetComponentsSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Boolean GetLoaded();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier4 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier4 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_UpdatedNetQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedNetQuery;
```

- `private Unity.Entities.EntityQuery m_AllNetQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllNetQuery;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Net.NetComponentsSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Net.NetComponentsSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public NetComponentsSystem()`  

```csharp
public NetComponentsSystem();
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

- `Game.Net.NetComponentsSystem+CheckNodeComponentsJob`  
- `Game.Net.NetComponentsSystem+TypeHandle`  

