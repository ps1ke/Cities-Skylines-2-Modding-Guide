# Game.Prefabs.UpdateFrameData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct UpdateFrameData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public System.Int32 m_UpdateGroupIndex;

    public UpdateFrameData(System.Int32 updateGroupIndex);

}
```


## Fields

- `public System.Int32 m_UpdateGroupIndex`  

```csharp
public System.Int32 m_UpdateGroupIndex;
```


## Constructors

- `public UpdateFrameData(System.Int32 updateGroupIndex)`  

```csharp
public UpdateFrameData(System.Int32 updateGroupIndex);
```


