# Game.Prefabs.BuildingExtensionPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.StaticObjectPrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class BuildingExtensionPrefab : Game.Prefabs.StaticObjectPrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Boolean m_ExternalLot;
    public Unity.Mathematics.float3 m_Position;
    public Unity.Mathematics.int2 m_OverrideLotSize;
    public System.Single m_OverrideHeight;

    public System.Collections.Generic.IEnumerable<System.String> modTags { get; }

    public BuildingExtensionPrefab();

    private System.Collections.Generic.IEnumerable<System.String> <>n__0();
    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Boolean m_ExternalLot`  

```csharp
public System.Boolean m_ExternalLot;
```

- `public Unity.Mathematics.float3 m_Position`  

```csharp
public Unity.Mathematics.float3 m_Position;
```

- `public Unity.Mathematics.int2 m_OverrideLotSize`  

```csharp
public Unity.Mathematics.int2 m_OverrideLotSize;
```

- `public System.Single m_OverrideHeight`  

```csharp
public System.Single m_OverrideHeight;
```


## Properties

- `public System.Collections.Generic.IEnumerable<System.String> modTags { get }`  

```csharp
public System.Collections.Generic.IEnumerable<System.String> modTags { get; }
```


## Constructors

- `public BuildingExtensionPrefab()`  

```csharp
public BuildingExtensionPrefab();
```


## Methods

- `private <>n__0() : System.Collections.Generic.IEnumerable<System.String>`  

```csharp
private System.Collections.Generic.IEnumerable<System.String> <>n__0();
```

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		base.GetArchetypeComponents(components);
		components.Add(ComponentType.ReadWrite<Extension>());
		components.Add(ComponentType.ReadWrite<SpawnLocationElement>());
		components.Add(ComponentType.ReadWrite<Color>());
		components.Add(ComponentType.ReadWrite<EnabledEffect>());
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<BuildingExtensionData>());
		components.Add(ComponentType.ReadWrite<Effect>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
	}
```


## Nested types

- `Game.Prefabs.BuildingExtensionPrefab+<get_modTags>d__8`  

