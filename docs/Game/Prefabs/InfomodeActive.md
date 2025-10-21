# Game.Prefabs.InfomodeActive

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct InfomodeActive : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public System.Int32 m_Priority;
    public System.Int32 m_Index;
    public System.Int32 m_SecondaryIndex;

    public InfomodeActive(System.Int32 priority, System.Int32 index, System.Int32 secondaryIndex);

}
```


## Fields

- `public System.Int32 m_Priority`  

```csharp
public System.Int32 m_Priority;
```

- `public System.Int32 m_Index`  

```csharp
public System.Int32 m_Index;
```

- `public System.Int32 m_SecondaryIndex`  

```csharp
public System.Int32 m_SecondaryIndex;
```


## Constructors

- `public InfomodeActive(System.Int32 priority, System.Int32 index, System.Int32 secondaryIndex)`  

```csharp
public InfomodeActive(System.Int32 priority, System.Int32 index, System.Int32 secondaryIndex);
```


