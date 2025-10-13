# Game.Prefabs.ToolErrorData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct ToolErrorData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Game.Tools.ErrorType m_Error;
    public Game.Prefabs.ToolErrorFlags m_Flags;

}
```


## Fields

- `public Game.Tools.ErrorType m_Error`  

```csharp
public Game.Tools.ErrorType m_Error;
```

- `public Game.Prefabs.ToolErrorFlags m_Flags`  

```csharp
public Game.Prefabs.ToolErrorFlags m_Flags;
```


