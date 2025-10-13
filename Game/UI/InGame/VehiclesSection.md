# Game.UI.InGame.VehiclesSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class VehiclesSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.UI.InGame.VehicleLocaleKey <vehicleKey>k__BackingField;
    private System.Int32 <vehicleCount>k__BackingField;
    private System.Int32 <availableVehicleCount>k__BackingField;
    private System.Int32 <vehicleCapacity>k__BackingField;
    private Unity.Collections.NativeList<Game.UI.InGame.VehiclesSection+UIVehicle> <vehicleList>k__BackingField;
    private Unity.Entities.DynamicBuffer<Game.Vehicles.OwnedVehicle> m_Buffer;
    private Unity.Entities.Entity m_CompanyEntity;

    protected System.String group { protected get; }
    private Game.UI.InGame.VehicleLocaleKey vehicleKey { private get; private set; }
    private System.Int32 vehicleCount { private get; private set; }
    private System.Int32 availableVehicleCount { private get; private set; }
    private System.Int32 vehicleCapacity { private get; private set; }
    private Unity.Collections.NativeList<Game.UI.InGame.VehiclesSection+UIVehicle> vehicleList { private get; private set; }

    public VehiclesSection();

    public static System.Void AddVehicle(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity vehicle, Unity.Collections.NativeList<Game.UI.InGame.VehiclesSection+UIVehicle> vehicleList);
    public static System.Void BindVehicle(Game.UI.NameSystem nameSystem, Colossal.UI.Binding.IJsonWriter binder, Game.UI.InGame.VehiclesSection+UIVehicle vehicle);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private Game.UI.InGame.VehicleLocaleKey <vehicleKey>k__BackingField`  

```csharp
private Game.UI.InGame.VehicleLocaleKey <vehicleKey>k__BackingField;
```

- `private System.Int32 <vehicleCount>k__BackingField`  

```csharp
private System.Int32 <vehicleCount>k__BackingField;
```

- `private System.Int32 <availableVehicleCount>k__BackingField`  

```csharp
private System.Int32 <availableVehicleCount>k__BackingField;
```

- `private System.Int32 <vehicleCapacity>k__BackingField`  

```csharp
private System.Int32 <vehicleCapacity>k__BackingField;
```

- `private Unity.Collections.NativeList<Game.UI.InGame.VehiclesSection+UIVehicle> <vehicleList>k__BackingField`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.VehiclesSection+UIVehicle> <vehicleList>k__BackingField;
```

- `private Unity.Entities.DynamicBuffer<Game.Vehicles.OwnedVehicle> m_Buffer`  

```csharp
private Unity.Entities.DynamicBuffer<Game.Vehicles.OwnedVehicle> m_Buffer;
```

- `private Unity.Entities.Entity m_CompanyEntity`  

```csharp
private Unity.Entities.Entity m_CompanyEntity;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private Game.UI.InGame.VehicleLocaleKey vehicleKey { private get; private set }`  

```csharp
private Game.UI.InGame.VehicleLocaleKey vehicleKey { private get; private set; }
```

- `private System.Int32 vehicleCount { private get; private set }`  

```csharp
private System.Int32 vehicleCount { private get; private set; }
```

- `private System.Int32 availableVehicleCount { private get; private set }`  

```csharp
private System.Int32 availableVehicleCount { private get; private set; }
```

- `private System.Int32 vehicleCapacity { private get; private set }`  

```csharp
private System.Int32 vehicleCapacity { private get; private set; }
```

- `private Unity.Collections.NativeList<Game.UI.InGame.VehiclesSection+UIVehicle> vehicleList { private get; private set }`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.VehiclesSection+UIVehicle> vehicleList { private get; private set; }
```


## Constructors

- `public VehiclesSection()`  

```csharp
public VehiclesSection();
```


## Methods

- `public static AddVehicle(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity vehicle, Unity.Collections.NativeList<Game.UI.InGame.VehiclesSection+UIVehicle> vehicleList) : System.Void`  

```csharp
public static System.Void AddVehicle(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity vehicle, Unity.Collections.NativeList<Game.UI.InGame.VehiclesSection+UIVehicle> vehicleList);
```

- `public static BindVehicle(Game.UI.NameSystem nameSystem, Colossal.UI.Binding.IJsonWriter binder, Game.UI.InGame.VehiclesSection+UIVehicle vehicle) : System.Void`  

```csharp
public static System.Void BindVehicle(Game.UI.NameSystem nameSystem, Colossal.UI.Binding.IJsonWriter binder, Game.UI.InGame.VehiclesSection+UIVehicle vehicle);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected virtual System.Void OnProcess();
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

- `Game.UI.InGame.VehiclesSection+UIVehicle`  

