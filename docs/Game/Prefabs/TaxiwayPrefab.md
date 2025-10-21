# Game.Prefabs.TaxiwayPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.NetGeometryPrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class TaxiwayPrefab : Game.Prefabs.NetGeometryPrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Single m_SpeedLimit;
    public System.Boolean m_Taxiway;
    public System.Boolean m_Runway;
    public System.Boolean m_Airspace;

    public TaxiwayPrefab();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public System.Single m_SpeedLimit`  

```csharp
public System.Single m_SpeedLimit;
```

- `public System.Boolean m_Taxiway`  

```csharp
public System.Boolean m_Taxiway;
```

- `public System.Boolean m_Runway`  

```csharp
public System.Boolean m_Runway;
```

- `public System.Boolean m_Airspace`  

```csharp
public System.Boolean m_Airspace;
```


## Constructors

- `public TaxiwayPrefab()`  

```csharp
public TaxiwayPrefab();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```


