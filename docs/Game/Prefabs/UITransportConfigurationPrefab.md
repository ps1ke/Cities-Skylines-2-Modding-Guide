# Game.Prefabs.UITransportConfigurationPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class UITransportConfigurationPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.InfoviewPrefab m_TransportInfoview;
    public Game.Prefabs.InfomodePrefab m_RoutesInfomode;
    public Game.Prefabs.PolicyPrefab m_TicketPricePolicy;
    public Game.Prefabs.PolicyPrefab m_OutOfServicePolicy;
    public Game.Prefabs.PolicyPrefab m_VehicleCountPolicy;
    public Game.Prefabs.PolicyPrefab m_DayRoutePolicy;
    public Game.Prefabs.PolicyPrefab m_NightRoutePolicy;
    public Game.Prefabs.UITransportSummaryItem[] m_PassengerSummaryItems;
    public Game.Prefabs.UITransportSummaryItem[] m_CargoSummaryItems;
    public Game.Prefabs.UITransportItem[] m_PassengerLineTypes;
    public Game.Prefabs.UITransportItem[] m_CargoLineTypes;

    public UITransportConfigurationPrefab();

    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public Game.Prefabs.InfoviewPrefab m_TransportInfoview`  

```csharp
public Game.Prefabs.InfoviewPrefab m_TransportInfoview;
```

- `public Game.Prefabs.InfomodePrefab m_RoutesInfomode`  

```csharp
public Game.Prefabs.InfomodePrefab m_RoutesInfomode;
```

- `public Game.Prefabs.PolicyPrefab m_TicketPricePolicy`  

```csharp
public Game.Prefabs.PolicyPrefab m_TicketPricePolicy;
```

- `public Game.Prefabs.PolicyPrefab m_OutOfServicePolicy`  

```csharp
public Game.Prefabs.PolicyPrefab m_OutOfServicePolicy;
```

- `public Game.Prefabs.PolicyPrefab m_VehicleCountPolicy`  

```csharp
public Game.Prefabs.PolicyPrefab m_VehicleCountPolicy;
```

- `public Game.Prefabs.PolicyPrefab m_DayRoutePolicy`  

```csharp
public Game.Prefabs.PolicyPrefab m_DayRoutePolicy;
```

- `public Game.Prefabs.PolicyPrefab m_NightRoutePolicy`  

```csharp
public Game.Prefabs.PolicyPrefab m_NightRoutePolicy;
```

- `public Game.Prefabs.UITransportSummaryItem[] m_PassengerSummaryItems`  

```csharp
public Game.Prefabs.UITransportSummaryItem[] m_PassengerSummaryItems;
```

- `public Game.Prefabs.UITransportSummaryItem[] m_CargoSummaryItems`  

```csharp
public Game.Prefabs.UITransportSummaryItem[] m_CargoSummaryItems;
```

- `public Game.Prefabs.UITransportItem[] m_PassengerLineTypes`  

```csharp
public Game.Prefabs.UITransportItem[] m_PassengerLineTypes;
```

- `public Game.Prefabs.UITransportItem[] m_CargoLineTypes`  

```csharp
public Game.Prefabs.UITransportItem[] m_CargoLineTypes;
```


## Constructors

- `public UITransportConfigurationPrefab()`  

```csharp
public UITransportConfigurationPrefab();
```


## Methods

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```


