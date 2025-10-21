# Game.Prefabs.CarBasePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class abstract public  

**Base:** `Game.Prefabs.VehiclePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

## Code

```csharp
public abstract class CarBasePrefab : Game.Prefabs.VehiclePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Vehicles.SizeClass m_SizeClass;
    public Game.Vehicles.EnergyTypes m_EnergyType;
    public System.Single m_MaxSpeed;
    public System.Single m_Acceleration;
    public System.Single m_Braking;
    public Unity.Mathematics.float2 m_Turning;
    public System.Single m_Stiffness;

    protected CarBasePrefab();

}
```


## Fields

- `public Game.Vehicles.SizeClass m_SizeClass`  

```csharp
public Game.Vehicles.SizeClass m_SizeClass;
```

- `public Game.Vehicles.EnergyTypes m_EnergyType`  

```csharp
public Game.Vehicles.EnergyTypes m_EnergyType;
```

- `public System.Single m_MaxSpeed`  

```csharp
public System.Single m_MaxSpeed;
```

- `public System.Single m_Acceleration`  

```csharp
public System.Single m_Acceleration;
```

- `public System.Single m_Braking`  

```csharp
public System.Single m_Braking;
```

- `public Unity.Mathematics.float2 m_Turning`  

```csharp
public Unity.Mathematics.float2 m_Turning;
```

- `public System.Single m_Stiffness`  

```csharp
public System.Single m_Stiffness;
```


## Constructors

- `protected CarBasePrefab()`  

```csharp
protected CarBasePrefab();
```


