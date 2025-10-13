# Game.Prefabs.WaterPipeConnection

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class WaterPipeConnection : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Int32 m_FreshCapacity;
    public System.Int32 m_SewageCapacity;
    public System.Int32 m_StormCapacity;

    public WaterPipeConnection();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public System.Int32 m_FreshCapacity`  

```csharp
public System.Int32 m_FreshCapacity;
```

- `public System.Int32 m_SewageCapacity`  

```csharp
public System.Int32 m_SewageCapacity;
```

- `public System.Int32 m_StormCapacity`  

```csharp
public System.Int32 m_StormCapacity;
```


## Constructors

- `public WaterPipeConnection()`  

```csharp
public WaterPipeConnection();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		if (components.Contains(ComponentType.ReadWrite<Edge>()))
		{
			components.Add(ComponentType.ReadWrite<Game.Net.WaterPipeConnection>());
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<WaterPipeConnectionData>());
	}
```


