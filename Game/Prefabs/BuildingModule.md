# Game.Prefabs.BuildingModule

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

## Code

```csharp
public sealed struct BuildingModule : Unity.Entities.IBufferElementData
{
    public Unity.Entities.Entity m_Module;

    public BuildingModule(Unity.Entities.Entity module);

}
```


## Fields

- `public Unity.Entities.Entity m_Module`  

```csharp
public Unity.Entities.Entity m_Module;
```


## Constructors

- `public BuildingModule(Unity.Entities.Entity module)`  

```csharp
public BuildingModule(Entity module)
	{
		m_Module = module;
	}
```


