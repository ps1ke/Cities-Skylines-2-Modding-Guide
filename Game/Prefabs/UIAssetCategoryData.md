# Game.Prefabs.UIAssetCategoryData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct UIAssetCategoryData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Entities.Entity m_Menu;

    public UIAssetCategoryData(Unity.Entities.Entity menu);

}
```


## Fields

- `public Unity.Entities.Entity m_Menu`  

```csharp
public Unity.Entities.Entity m_Menu;
```


## Constructors

- `public UIAssetCategoryData(Unity.Entities.Entity menu)`  

```csharp
public UIAssetCategoryData(Entity menu)
	{
		m_Menu = menu;
	}
```


