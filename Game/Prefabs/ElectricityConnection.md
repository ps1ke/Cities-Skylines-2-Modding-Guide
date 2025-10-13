# Game.Prefabs.ElectricityConnection

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ElectricityConnection : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.ElectricityConnection+Voltage m_Voltage;
    public Game.Net.FlowDirection m_Direction;
    public System.Int32 m_Capacity;
    public Game.Prefabs.NetPieceRequirements[] m_RequireAll;
    public Game.Prefabs.NetPieceRequirements[] m_RequireAny;
    public Game.Prefabs.NetPieceRequirements[] m_RequireNone;

    public ElectricityConnection();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public Game.Prefabs.ElectricityConnection+Voltage m_Voltage`  

```csharp
public Game.Prefabs.ElectricityConnection+Voltage m_Voltage;
```

- `public Game.Net.FlowDirection m_Direction`  

```csharp
public Game.Net.FlowDirection m_Direction;
```

- `public System.Int32 m_Capacity`  

```csharp
public System.Int32 m_Capacity;
```

- `public Game.Prefabs.NetPieceRequirements[] m_RequireAll`  

```csharp
public Game.Prefabs.NetPieceRequirements[] m_RequireAll;
```

- `public Game.Prefabs.NetPieceRequirements[] m_RequireAny`  

```csharp
public Game.Prefabs.NetPieceRequirements[] m_RequireAny;
```

- `public Game.Prefabs.NetPieceRequirements[] m_RequireNone`  

```csharp
public Game.Prefabs.NetPieceRequirements[] m_RequireNone;
```


## Constructors

- `public ElectricityConnection()`  

```csharp
public ElectricityConnection();
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


## Nested types

- `Game.Prefabs.ElectricityConnection+Voltage`  

