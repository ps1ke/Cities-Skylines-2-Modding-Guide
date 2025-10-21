# Game.UI.InGame.VehicleCountSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class VehicleCountSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.UI.InGame.PoliciesUISystem m_PoliciesUISystem;
    private Unity.Entities.Entity m_VehicleCountPolicy;
    private Unity.Entities.EntityQuery m_ConfigQuery;
    private Unity.Collections.NativeArray<System.Int32> m_IntResults;
    private Unity.Collections.NativeReference<System.Single> m_DurationResult;
    private System.Int32 <vehicleCountMin>k__BackingField;
    private System.Int32 <vehicleCountMax>k__BackingField;
    private System.Int32 <vehicleCount>k__BackingField;
    private System.Int32 <activeVehicles>k__BackingField;
    private System.Single <stableDuration>k__BackingField;
    private Game.UI.InGame.VehicleCountSection+TypeHandle __TypeHandle;

    protected System.String group { protected get; }
    private System.Int32 vehicleCountMin { private get; private set; }
    private System.Int32 vehicleCountMax { private get; private set; }
    private System.Int32 vehicleCount { private get; private set; }
    private System.Int32 activeVehicles { private get; private set; }
    private System.Single stableDuration { private get; private set; }

    public VehicleCountSection();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnProcess();
    private System.Void OnSetVehicleCount(System.Single newVehicleCount);
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private Game.UI.InGame.PoliciesUISystem m_PoliciesUISystem`  

```csharp
private Game.UI.InGame.PoliciesUISystem m_PoliciesUISystem;
```

- `private Unity.Entities.Entity m_VehicleCountPolicy`  

```csharp
private Unity.Entities.Entity m_VehicleCountPolicy;
```

- `private Unity.Entities.EntityQuery m_ConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConfigQuery;
```

- `private Unity.Collections.NativeArray<System.Int32> m_IntResults`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_IntResults;
```

- `private Unity.Collections.NativeReference<System.Single> m_DurationResult`  

```csharp
private Unity.Collections.NativeReference<System.Single> m_DurationResult;
```

- `private System.Int32 <vehicleCountMin>k__BackingField`  

```csharp
private System.Int32 <vehicleCountMin>k__BackingField;
```

- `private System.Int32 <vehicleCountMax>k__BackingField`  

```csharp
private System.Int32 <vehicleCountMax>k__BackingField;
```

- `private System.Int32 <vehicleCount>k__BackingField`  

```csharp
private System.Int32 <vehicleCount>k__BackingField;
```

- `private System.Int32 <activeVehicles>k__BackingField`  

```csharp
private System.Int32 <activeVehicles>k__BackingField;
```

- `private System.Single <stableDuration>k__BackingField`  

```csharp
private System.Single <stableDuration>k__BackingField;
```

- `private Game.UI.InGame.VehicleCountSection+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.VehicleCountSection+TypeHandle __TypeHandle;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Int32 vehicleCountMin { private get; private set }`  

```csharp
private System.Int32 vehicleCountMin { private get; private set; }
```

- `private System.Int32 vehicleCountMax { private get; private set }`  

```csharp
private System.Int32 vehicleCountMax { private get; private set; }
```

- `private System.Int32 vehicleCount { private get; private set }`  

```csharp
private System.Int32 vehicleCount { private get; private set; }
```

- `private System.Int32 activeVehicles { private get; private set }`  

```csharp
private System.Int32 activeVehicles { private get; private set; }
```

- `private System.Single stableDuration { private get; private set }`  

```csharp
private System.Single stableDuration { private get; private set; }
```


## Constructors

- `public VehicleCountSection()`  

```csharp
public VehicleCountSection();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
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

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected virtual System.Void OnProcess();
```

- `private OnSetVehicleCount(System.Single newVehicleCount) : System.Void`  

```csharp
private System.Void OnSetVehicleCount(System.Single newVehicleCount);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
```

- `protected virtual Reset() : System.Void`  

```csharp
protected virtual System.Void Reset();
```

- `private Visible() : System.Boolean`  

```csharp
private System.Boolean Visible();
```


## Nested types

- `Game.UI.InGame.VehicleCountSection+Result`  
- `Game.UI.InGame.VehicleCountSection+CalculateVehicleCountJob`  
- `Game.UI.InGame.VehicleCountSection+TypeHandle`  

