# Game.Objects.SubObjectSystem+SubObjectData

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IComparable<Game.Objects.SubObjectSystem+SubObjectData>`  

## Code

```csharp
public sealed struct SubObjectData : System.IComparable<Game.Objects.SubObjectSystem+SubObjectData>
{
    public Unity.Entities.Entity m_SubObject;
    public System.Single m_Radius;

    public SubObjectData(Unity.Entities.Entity subObject, System.Single radius);

    public System.Int32 CompareTo(Game.Objects.SubObjectSystem+SubObjectData other);
}
```


## Fields

- `public Unity.Entities.Entity m_SubObject`  

```csharp
public Unity.Entities.Entity m_SubObject;
```

- `public System.Single m_Radius`  

```csharp
public System.Single m_Radius;
```


## Constructors

- `public SubObjectData(Unity.Entities.Entity subObject, System.Single radius)`  

```csharp
public SubObjectData(Unity.Entities.Entity subObject, System.Single radius);
```


## Methods

- `public CompareTo(Game.Objects.SubObjectSystem+SubObjectData other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Game.Objects.SubObjectSystem+SubObjectData other);
```


