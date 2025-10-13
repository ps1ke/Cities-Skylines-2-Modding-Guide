# Game.Prefabs.TerrainPropertiesPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

## Code

```csharp
public class TerrainPropertiesPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Simulation.WaterSystem+WaterSource[] m_WaterSources;
    public System.Int32 m_WaterSourceSteps;
    public System.Int32 m_WaterVelocitySteps;
    public System.Int32 m_WaterDepthSteps;
    public System.Int32 m_WaterMaxSpeed;

    public TerrainPropertiesPrefab();

    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public Game.Simulation.WaterSystem+WaterSource[] m_WaterSources`  

```csharp
public Game.Simulation.WaterSystem+WaterSource[] m_WaterSources;
```

- `public System.Int32 m_WaterSourceSteps`  

```csharp
public System.Int32 m_WaterSourceSteps;
```

- `public System.Int32 m_WaterVelocitySteps`  

```csharp
public System.Int32 m_WaterVelocitySteps;
```

- `public System.Int32 m_WaterDepthSteps`  

```csharp
public System.Int32 m_WaterDepthSteps;
```

- `public System.Int32 m_WaterMaxSpeed`  

```csharp
public System.Int32 m_WaterMaxSpeed;
```


## Constructors

- `public TerrainPropertiesPrefab()`  

```csharp
public TerrainPropertiesPrefab();
```


## Methods

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```


