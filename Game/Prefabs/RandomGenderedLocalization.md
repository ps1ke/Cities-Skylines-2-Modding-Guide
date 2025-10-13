# Game.Prefabs.RandomGenderedLocalization

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.RandomLocalization`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class RandomGenderedLocalization : Game.Prefabs.RandomLocalization, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.String m_MaleID;
    public System.String m_FemaleID;

    public RandomGenderedLocalization();

    protected virtual System.Int32 GetLocalizationCount();
}
```


## Fields

- `public System.String m_MaleID`  

```csharp
public System.String m_MaleID;
```

- `public System.String m_FemaleID`  

```csharp
public System.String m_FemaleID;
```


## Constructors

- `public RandomGenderedLocalization()`  

```csharp
public RandomGenderedLocalization();
```


## Methods

- `protected virtual GetLocalizationCount() : System.Int32`  

```csharp
protected override int GetLocalizationCount()
	{
		int localizationCount = base.GetLocalizationCount();
		int localizationIndexCount = RandomLocalization.GetLocalizationIndexCount(base.prefab, m_MaleID);
		int localizationIndexCount2 = RandomLocalization.GetLocalizationIndexCount(base.prefab, m_FemaleID);
		int num = math.min(localizationCount, math.min(localizationIndexCount, localizationIndexCount2));
		if (localizationCount != num || localizationIndexCount != num || localizationIndexCount2 != num)
		{
			ComponentBase.baseLog.WarnFormat(base.prefab, "All gendered localization IDs should have the same variation count: {0} ({1}), {2} ({3}), {4} ({5})", m_LocalizationID, localizationCount, m_MaleID, localizationIndexCount, m_FemaleID, localizationIndexCount2);
		}
		return num;
	}
```


