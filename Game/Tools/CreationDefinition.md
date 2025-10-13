# Game.Tools.CreationDefinition

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct CreationDefinition : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Entities.Entity m_Prefab;
    public Unity.Entities.Entity m_SubPrefab;
    public Unity.Entities.Entity m_Original;
    public Unity.Entities.Entity m_Owner;
    public Unity.Entities.Entity m_Attached;
    public Game.Tools.CreationFlags m_Flags;
    public System.Int32 m_RandomSeed;

}
```


## Fields

- `public Unity.Entities.Entity m_Prefab`  

```csharp
public Unity.Entities.Entity m_Prefab;
```

- `public Unity.Entities.Entity m_SubPrefab`  

```csharp
public Unity.Entities.Entity m_SubPrefab;
```

- `public Unity.Entities.Entity m_Original`  

```csharp
public Unity.Entities.Entity m_Original;
```

- `public Unity.Entities.Entity m_Owner`  

```csharp
public Unity.Entities.Entity m_Owner;
```

- `public Unity.Entities.Entity m_Attached`  

```csharp
public Unity.Entities.Entity m_Attached;
```

- `public Game.Tools.CreationFlags m_Flags`  

```csharp
public Game.Tools.CreationFlags m_Flags;
```

- `public System.Int32 m_RandomSeed`  

```csharp
public System.Int32 m_RandomSeed;
```


