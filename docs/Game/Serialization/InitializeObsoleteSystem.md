# Game.Serialization.InitializeObsoleteSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class InitializeObsoleteSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_ObsoleteQuery;
    private Unity.Entities.EntityQuery m_MeshSettingsQuery;
    private System.Collections.Generic.HashSet<Unity.Entities.ComponentType> m_ArchetypeComponents;
    private System.Collections.Generic.Dictionary<System.Type, Game.Prefabs.PrefabBase> m_PrefabInstances;
    private Game.Serialization.InitializeObsoleteSystem+TypeHandle __TypeHandle;

    public InitializeObsoleteSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Unity.Entities.EntityArchetype GetArchetype<T>();
    private Unity.Entities.EntityArchetype GetArchetype<T, TComponentType>();
    private Unity.Entities.EntityArchetype GetArchetype<T, TComponentType1, TComponentType2>();
    private Unity.Entities.EntityArchetype GetArchetype<T, TComponentType1, TComponentType2, TComponentType3>();
    private T GetPrefabInstance<T>();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_ObsoleteQuery`  

```csharp
private Unity.Entities.EntityQuery m_ObsoleteQuery;
```

- `private Unity.Entities.EntityQuery m_MeshSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_MeshSettingsQuery;
```

- `private System.Collections.Generic.HashSet<Unity.Entities.ComponentType> m_ArchetypeComponents`  

```csharp
private System.Collections.Generic.HashSet<Unity.Entities.ComponentType> m_ArchetypeComponents;
```

- `private System.Collections.Generic.Dictionary<System.Type, Game.Prefabs.PrefabBase> m_PrefabInstances`  

```csharp
private System.Collections.Generic.Dictionary<System.Type, Game.Prefabs.PrefabBase> m_PrefabInstances;
```

- `private Game.Serialization.InitializeObsoleteSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.InitializeObsoleteSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public InitializeObsoleteSystem()`  

```csharp
public InitializeObsoleteSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private GetArchetype<T>() : Unity.Entities.EntityArchetype`  

```csharp
private Unity.Entities.EntityArchetype GetArchetype<T>();
```

- `private GetArchetype<T, TComponentType>() : Unity.Entities.EntityArchetype`  

```csharp
private Unity.Entities.EntityArchetype GetArchetype<T, TComponentType>();
```

- `private GetArchetype<T, TComponentType1, TComponentType2>() : Unity.Entities.EntityArchetype`  

```csharp
private Unity.Entities.EntityArchetype GetArchetype<T, TComponentType1, TComponentType2>();
```

- `private GetArchetype<T, TComponentType1, TComponentType2, TComponentType3>() : Unity.Entities.EntityArchetype`  

```csharp
private Unity.Entities.EntityArchetype GetArchetype<T, TComponentType1, TComponentType2, TComponentType3>();
```

- `private GetPrefabInstance<T>() : T`  

```csharp
private T GetPrefabInstance<T>();
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

- `Game.Serialization.InitializeObsoleteSystem+InitializeObsoleteJob`  
- `Game.Serialization.InitializeObsoleteSystem+TypeHandle`  

