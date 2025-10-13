# Game.Prefabs.DlcRequirement

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ContentRequirementBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class DlcRequirement : Game.Prefabs.ContentRequirementBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Colossal.PSI.Common.DlcId m_Dlc;

    public DlcRequirement();

    public virtual System.Boolean CheckRequirement();
    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.String GetDebugString();
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public Colossal.PSI.Common.DlcId m_Dlc`  

```csharp
public Colossal.PSI.Common.DlcId m_Dlc;
```


## Constructors

- `public DlcRequirement()`  

```csharp
public DlcRequirement();
```


## Methods

- `public virtual CheckRequirement() : System.Boolean`  

```csharp
public override bool CheckRequirement()
	{
		return PlatformManager.instance.IsDlcOwned(m_Dlc);
	}
```

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
	}
```

- `public virtual GetDebugString() : System.String`  

```csharp
public override string GetDebugString()
	{
		return PlatformManager.instance.GetDlcName(m_Dlc).Nicify() + " DLC";
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
	}
```


