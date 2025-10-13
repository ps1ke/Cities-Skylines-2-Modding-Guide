# Game.Prefabs.NetStatusInfomodePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.GradientInfomodeBasePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`, `Game.Prefabs.IGradientInfomode`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class NetStatusInfomodePrefab : Game.Prefabs.GradientInfomodeBasePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase, Game.Prefabs.IGradientInfomode
{
    public Game.Prefabs.NetStatusType m_Type;
    public Colossal.Mathematics.Bounds1 m_Range;
    public System.Single m_FlowSpeed;
    public System.Single m_FlowTiling;
    public System.Single m_MinFlow;

    public System.String infomodeTypeLocaleKey { get; }

    public NetStatusInfomodePrefab();

    public virtual System.Boolean CanActivateBoth(Game.Prefabs.InfomodePrefab other);
    public virtual System.Void GetColors(UnityEngine.Color& color0, UnityEngine.Color& color1, UnityEngine.Color& color2, System.Single& steps, System.Single& speed, System.Single& tiling, System.Single& fill);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    private System.Boolean VisibleOnRoadSurface();
}
```


## Fields

- `public Game.Prefabs.NetStatusType m_Type`  

```csharp
public Game.Prefabs.NetStatusType m_Type;
```

- `public Colossal.Mathematics.Bounds1 m_Range`  

```csharp
public Colossal.Mathematics.Bounds1 m_Range;
```

- `public System.Single m_FlowSpeed`  

```csharp
public System.Single m_FlowSpeed;
```

- `public System.Single m_FlowTiling`  

```csharp
public System.Single m_FlowTiling;
```

- `public System.Single m_MinFlow`  

```csharp
public System.Single m_MinFlow;
```


## Properties

- `public System.String infomodeTypeLocaleKey { get }`  

```csharp
public System.String infomodeTypeLocaleKey { get; }
```


## Constructors

- `public NetStatusInfomodePrefab()`  

```csharp
public NetStatusInfomodePrefab();
```


## Methods

- `public virtual CanActivateBoth(Game.Prefabs.InfomodePrefab other) : System.Boolean`  

```csharp
public override bool CanActivateBoth(InfomodePrefab other)
	{
		if (other is NetStatusInfomodePrefab netStatusInfomodePrefab && VisibleOnRoadSurface() && netStatusInfomodePrefab.VisibleOnRoadSurface())
		{
			return false;
		}
		return base.CanActivateBoth(other);
	}
```

- `public virtual GetColors(UnityEngine.Color& color0, UnityEngine.Color& color1, UnityEngine.Color& color2, System.Single& steps, System.Single& speed, System.Single& tiling, System.Single& fill) : System.Void`  

```csharp
public override void GetColors(out Color color0, out Color color1, out Color color2, out float steps, out float speed, out float tiling, out float fill)
	{
		base.GetColors(out color0, out color1, out color2, out steps, out speed, out tiling, out fill);
		speed = m_FlowSpeed;
		if (m_FlowTiling != 0f)
		{
			tiling = 1f / m_FlowTiling;
		}
		if (m_MinFlow != 0f)
		{
			fill = 1f / m_MinFlow;
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<InfoviewNetStatusData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		InfoviewNetStatusData componentData = new InfoviewNetStatusData
		{
			m_Type = m_Type,
			m_Range = m_Range
		};
		if (m_FlowTiling != 0f)
		{
			componentData.m_Tiling = 1f / m_FlowTiling;
		}
		entityManager.SetComponentData(entity, componentData);
	}
```

- `private VisibleOnRoadSurface() : System.Boolean`  

```csharp
private bool VisibleOnRoadSurface()
	{
		NetStatusType type = m_Type;
		if ((uint)type <= 4u)
		{
			return true;
		}
		return false;
	}
```


