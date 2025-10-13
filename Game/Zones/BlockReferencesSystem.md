# Game.Zones.BlockReferencesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Zones`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BlockReferencesSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_BlockQuery;
    private Game.Zones.BlockReferencesSystem+TypeHandle __TypeHandle;

    public BlockReferencesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_BlockQuery`  

```csharp
private Unity.Entities.EntityQuery m_BlockQuery;
```

- `private Game.Zones.BlockReferencesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Zones.BlockReferencesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public BlockReferencesSystem()`  

```csharp
public BlockReferencesSystem();
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

- `Game.Zones.BlockReferencesSystem+UpdateBlockReferencesJob`  
- `Game.Zones.BlockReferencesSystem+TypeHandle`  

