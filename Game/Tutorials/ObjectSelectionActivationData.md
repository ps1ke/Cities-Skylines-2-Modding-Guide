# Game.Tutorials.ObjectSelectionActivationData

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

## Code

```csharp
public sealed struct ObjectSelectionActivationData : Unity.Entities.IBufferElementData
{
    public Unity.Entities.Entity m_Prefab;
    public System.Boolean m_AllowTool;

    public ObjectSelectionActivationData(Unity.Entities.Entity prefab, System.Boolean allowTool);

}
```


## Fields

- `public Unity.Entities.Entity m_Prefab`  

```csharp
public Unity.Entities.Entity m_Prefab;
```

- `public System.Boolean m_AllowTool`  

```csharp
public System.Boolean m_AllowTool;
```


## Constructors

- `public ObjectSelectionActivationData(Unity.Entities.Entity prefab, System.Boolean allowTool)`  

```csharp
public ObjectSelectionActivationData(Entity prefab, bool allowTool)
	{
		m_Prefab = prefab;
		m_AllowTool = allowTool;
	}
```


