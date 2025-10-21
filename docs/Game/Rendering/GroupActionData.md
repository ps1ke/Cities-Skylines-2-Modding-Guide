# Game.Rendering.BatchInstanceSystem+GroupActionData

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IComparable<Game.Rendering.BatchInstanceSystem+GroupActionData>`  

## Code

```csharp
public sealed struct GroupActionData : System.IComparable<Game.Rendering.BatchInstanceSystem+GroupActionData>
{
    public System.Int32 m_GroupIndex;
    public System.Int32 m_RemoveInstanceIndex;
    public System.Int32 m_MergeIndex;
    public Game.Rendering.InstanceData m_AddInstanceData;
    public System.Boolean m_FadeIn;

    public System.Int32 CompareTo(Game.Rendering.BatchInstanceSystem+GroupActionData other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public System.Int32 m_GroupIndex`  

```csharp
public System.Int32 m_GroupIndex;
```

- `public System.Int32 m_RemoveInstanceIndex`  

```csharp
public System.Int32 m_RemoveInstanceIndex;
```

- `public System.Int32 m_MergeIndex`  

```csharp
public System.Int32 m_MergeIndex;
```

- `public Game.Rendering.InstanceData m_AddInstanceData`  

```csharp
public Game.Rendering.InstanceData m_AddInstanceData;
```

- `public System.Boolean m_FadeIn`  

```csharp
public System.Boolean m_FadeIn;
```


## Methods

- `public CompareTo(Game.Rendering.BatchInstanceSystem+GroupActionData other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Game.Rendering.BatchInstanceSystem+GroupActionData other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


