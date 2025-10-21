# Game.Simulation.CountResidentialPropertySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CountResidentialPropertySystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Colossal.Collections.NativeAccumulator<Game.Simulation.CountResidentialPropertySystem+ResidentialPropertyData> m_ResidentialPropertyData;
    private Game.Simulation.CountResidentialPropertySystem+ResidentialPropertyData m_LastResidentialPropertyData;
    private Unity.Entities.EntityQuery m_ResidentialPropertyQuery;
    private Game.Simulation.CountResidentialPropertySystem+TypeHandle __TypeHandle;

    public Unity.Mathematics.int3 FreeProperties { get; }
    public Unity.Mathematics.int3 TotalProperties { get; }
    public System.Int32 FreeShelterCapacity { get; }
    public System.Int32 TotalShelterCapacity { get; }

    public CountResidentialPropertySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void Deserialize<TReader>(TReader reader);
    public Game.Simulation.CountResidentialPropertySystem+ResidentialPropertyData GetResidentialPropertyData();
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Colossal.Collections.NativeAccumulator<Game.Simulation.CountResidentialPropertySystem+ResidentialPropertyData> m_ResidentialPropertyData`  

```csharp
private Colossal.Collections.NativeAccumulator<Game.Simulation.CountResidentialPropertySystem+ResidentialPropertyData> m_ResidentialPropertyData;
```

- `private Game.Simulation.CountResidentialPropertySystem+ResidentialPropertyData m_LastResidentialPropertyData`  

```csharp
private Game.Simulation.CountResidentialPropertySystem+ResidentialPropertyData m_LastResidentialPropertyData;
```

- `private Unity.Entities.EntityQuery m_ResidentialPropertyQuery`  

```csharp
private Unity.Entities.EntityQuery m_ResidentialPropertyQuery;
```

- `private Game.Simulation.CountResidentialPropertySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CountResidentialPropertySystem+TypeHandle __TypeHandle;
```


## Properties

- `public Unity.Mathematics.int3 FreeProperties { get }`  

```csharp
public Unity.Mathematics.int3 FreeProperties { get; }
```

- `public Unity.Mathematics.int3 TotalProperties { get }`  

```csharp
public Unity.Mathematics.int3 TotalProperties { get; }
```

- `public System.Int32 FreeShelterCapacity { get }`  

```csharp
public System.Int32 FreeShelterCapacity { get; }
```

- `public System.Int32 TotalShelterCapacity { get }`  

```csharp
public System.Int32 TotalShelterCapacity { get; }
```


## Constructors

- `public CountResidentialPropertySystem()`  

```csharp
public CountResidentialPropertySystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetResidentialPropertyData() : Game.Simulation.CountResidentialPropertySystem+ResidentialPropertyData`  

```csharp
public Game.Simulation.CountResidentialPropertySystem+ResidentialPropertyData GetResidentialPropertyData();
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
```


## Nested types

- `Game.Simulation.CountResidentialPropertySystem+ResidentialPropertyData`  
- `Game.Simulation.CountResidentialPropertySystem+CountResidentialPropertyJob`  
- `Game.Simulation.CountResidentialPropertySystem+TypeHandle`  

