# Game.Serialization.SerializerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class SerializerSystem : Game.GameSystemBase
{
    private System.Int32 <totalSize>k__BackingField;
    private Game.Serialization.SaveGameSystem m_SaveGameSystem;
    private Game.Serialization.LoadGameSystem m_LoadGameSystem;
    private Game.Serialization.WriteSystem m_WriteSystem;
    private Game.Serialization.ReadSystem m_ReadSystem;
    private Game.UpdateSystem m_UpdateSystem;
    private Colossal.Serialization.Entities.ComponentSerializerLibrary m_ComponentSerializerLibrary;
    private Colossal.Serialization.Entities.SystemSerializerLibrary m_SystemSerializerLibrary;
    private Unity.Entities.EntityQuery m_Query;

    public Colossal.Serialization.Entities.ComponentSerializerLibrary componentLibrary { get; }
    public Colossal.Serialization.Entities.SystemSerializerLibrary systemLibrary { get; }
    public System.Int32 totalSize { get; set; }

    public SerializerSystem();

    private System.Void CreateQuery(System.Collections.Generic.IEnumerable<Unity.Entities.ComponentType> serializableComponents);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void SetDirty();
}
```


## Fields

- `private System.Int32 <totalSize>k__BackingField`  

```csharp
private System.Int32 <totalSize>k__BackingField;
```

- `private Game.Serialization.SaveGameSystem m_SaveGameSystem`  

```csharp
private Game.Serialization.SaveGameSystem m_SaveGameSystem;
```

- `private Game.Serialization.LoadGameSystem m_LoadGameSystem`  

```csharp
private Game.Serialization.LoadGameSystem m_LoadGameSystem;
```

- `private Game.Serialization.WriteSystem m_WriteSystem`  

```csharp
private Game.Serialization.WriteSystem m_WriteSystem;
```

- `private Game.Serialization.ReadSystem m_ReadSystem`  

```csharp
private Game.Serialization.ReadSystem m_ReadSystem;
```

- `private Game.UpdateSystem m_UpdateSystem`  

```csharp
private Game.UpdateSystem m_UpdateSystem;
```

- `private Colossal.Serialization.Entities.ComponentSerializerLibrary m_ComponentSerializerLibrary`  

```csharp
private Colossal.Serialization.Entities.ComponentSerializerLibrary m_ComponentSerializerLibrary;
```

- `private Colossal.Serialization.Entities.SystemSerializerLibrary m_SystemSerializerLibrary`  

```csharp
private Colossal.Serialization.Entities.SystemSerializerLibrary m_SystemSerializerLibrary;
```

- `private Unity.Entities.EntityQuery m_Query`  

```csharp
private Unity.Entities.EntityQuery m_Query;
```


## Properties

- `public Colossal.Serialization.Entities.ComponentSerializerLibrary componentLibrary { get }`  

```csharp
public Colossal.Serialization.Entities.ComponentSerializerLibrary componentLibrary { get; }
```

- `public Colossal.Serialization.Entities.SystemSerializerLibrary systemLibrary { get }`  

```csharp
public Colossal.Serialization.Entities.SystemSerializerLibrary systemLibrary { get; }
```

- `public System.Int32 totalSize { get; set }`  

```csharp
public System.Int32 totalSize { get; set; }
```


## Constructors

- `public SerializerSystem()`  

```csharp
public SerializerSystem();
```


## Methods

- `private CreateQuery(System.Collections.Generic.IEnumerable<Unity.Entities.ComponentType> serializableComponents) : System.Void`  

```csharp
private System.Void CreateQuery(System.Collections.Generic.IEnumerable<Unity.Entities.ComponentType> serializableComponents);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public SetDirty() : System.Void`  

```csharp
public System.Void SetDirty();
```


