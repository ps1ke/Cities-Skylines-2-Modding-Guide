# Game.Prefabs.ZonePrefabs

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `DefaultMember`  

## Code

```csharp
public sealed struct ZonePrefabs
{
    private Unity.Collections.NativeArray<Unity.Entities.Entity> m_ZonePrefabs;

    public Unity.Entities.Entity Item { get; }

    public ZonePrefabs(Unity.Collections.NativeArray<Unity.Entities.Entity> zonePrefabs);

}
```


## Fields

- `private Unity.Collections.NativeArray<Unity.Entities.Entity> m_ZonePrefabs`  

```csharp
private Unity.Collections.NativeArray<Unity.Entities.Entity> m_ZonePrefabs;
```


## Properties

- `public Unity.Entities.Entity Item { get }`  

```csharp
public Unity.Entities.Entity Item { get; }
```


## Constructors

- `public ZonePrefabs(Unity.Collections.NativeArray<Unity.Entities.Entity> zonePrefabs)`  

```csharp
public ZonePrefabs(NativeArray<Entity> zonePrefabs)
	{
		m_ZonePrefabs = zonePrefabs;
	}
```


