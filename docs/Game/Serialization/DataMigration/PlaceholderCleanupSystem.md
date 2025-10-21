# Game.Serialization.DataMigration.PlaceholderCleanupSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization.DataMigration`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PlaceholderCleanupSystem : Game.GameSystemBase
{
    private Game.Serialization.LoadGameSystem m_LoadGameSystem;
    private Game.Serialization.DeserializationBarrier m_DeserializationBarrier;
    private Unity.Entities.EntityQuery m_Query;
    private Unity.Entities.ComponentTypeSet m_ComponentSet;
    private Game.Serialization.DataMigration.PlaceholderCleanupSystem+TypeHandle __TypeHandle;

    public PlaceholderCleanupSystem();

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

- `private Game.Serialization.DeserializationBarrier m_DeserializationBarrier`  

```csharp
private Game.Serialization.DeserializationBarrier m_DeserializationBarrier;
```

- `private Unity.Entities.EntityQuery m_Query`  

```csharp
private Unity.Entities.EntityQuery m_Query;
```

- `private Unity.Entities.ComponentTypeSet m_ComponentSet`  

```csharp
private Unity.Entities.ComponentTypeSet m_ComponentSet;
```

- `private Game.Serialization.DataMigration.PlaceholderCleanupSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.DataMigration.PlaceholderCleanupSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public PlaceholderCleanupSystem()`  

```csharp
public PlaceholderCleanupSystem();
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

- `Game.Serialization.DataMigration.PlaceholderCleanupSystem+PlaceholderCleanupJob`  
- `Game.Serialization.DataMigration.PlaceholderCleanupSystem+TypeHandle`  

