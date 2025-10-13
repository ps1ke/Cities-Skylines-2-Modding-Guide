# Game.Prefabs.ObjectRequirementElement

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct ObjectRequirementElement : Unity.Entities.IBufferElementData
{
    public Unity.Entities.Entity m_Requirement;
    public System.UInt16 m_Group;
    public Game.Prefabs.ObjectRequirementType m_Type;
    public Game.Prefabs.ObjectRequirementFlags m_RequireFlags;
    public Game.Prefabs.ObjectRequirementFlags m_ForbidFlags;

    public ObjectRequirementElement(Unity.Entities.Entity requirement, System.Int32 group, Game.Prefabs.ObjectRequirementType type);
    public ObjectRequirementElement(Game.Prefabs.ObjectRequirementFlags require, Game.Prefabs.ObjectRequirementFlags forbid, System.Int32 group, Game.Prefabs.ObjectRequirementType type);

}
```


## Fields

- `public Unity.Entities.Entity m_Requirement`  

```csharp
public Unity.Entities.Entity m_Requirement;
```

- `public System.UInt16 m_Group`  

```csharp
public System.UInt16 m_Group;
```

- `public Game.Prefabs.ObjectRequirementType m_Type`  

```csharp
public Game.Prefabs.ObjectRequirementType m_Type;
```

- `public Game.Prefabs.ObjectRequirementFlags m_RequireFlags`  

```csharp
public Game.Prefabs.ObjectRequirementFlags m_RequireFlags;
```

- `public Game.Prefabs.ObjectRequirementFlags m_ForbidFlags`  

```csharp
public Game.Prefabs.ObjectRequirementFlags m_ForbidFlags;
```


## Constructors

- `public ObjectRequirementElement(Unity.Entities.Entity requirement, System.Int32 group, Game.Prefabs.ObjectRequirementType type = 0)`  

```csharp
public ObjectRequirementElement(Unity.Entities.Entity requirement, System.Int32 group, Game.Prefabs.ObjectRequirementType type);
```

- `public ObjectRequirementElement(Game.Prefabs.ObjectRequirementFlags require, Game.Prefabs.ObjectRequirementFlags forbid, System.Int32 group, Game.Prefabs.ObjectRequirementType type = 0)`  

```csharp
public ObjectRequirementElement(Game.Prefabs.ObjectRequirementFlags require, Game.Prefabs.ObjectRequirementFlags forbid, System.Int32 group, Game.Prefabs.ObjectRequirementType type);
```


