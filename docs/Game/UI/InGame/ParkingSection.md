# Game.UI.InGame.ParkingSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ParkingSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Int32 <parkingFee>k__BackingField;
    private System.Int32 <parkedCars>k__BackingField;
    private System.Int32 <parkingCapacity>k__BackingField;

    protected System.String group { protected get; }
    private System.Int32 parkingFee { private get; private set; }
    private System.Int32 parkedCars { private get; private set; }
    private System.Int32 parkingCapacity { private get; private set; }

    public ParkingSection();

    private System.Void CheckParkingLanes(Unity.Entities.DynamicBuffer<Game.Objects.SubObject> subObjects, System.Int32& laneCount);
    private System.Void CheckParkingLanes(Unity.Entities.DynamicBuffer<Game.Net.SubNet> subNets, System.Int32& laneCount);
    private System.Void CheckParkingLanes(Unity.Entities.DynamicBuffer<Game.Net.SubLane> subLanes, System.Int32& laneCount);
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private System.Int32 <parkingFee>k__BackingField`  

```csharp
private System.Int32 <parkingFee>k__BackingField;
```

- `private System.Int32 <parkedCars>k__BackingField`  

```csharp
private System.Int32 <parkedCars>k__BackingField;
```

- `private System.Int32 <parkingCapacity>k__BackingField`  

```csharp
private System.Int32 <parkingCapacity>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Int32 parkingFee { private get; private set }`  

```csharp
private System.Int32 parkingFee { private get; private set; }
```

- `private System.Int32 parkedCars { private get; private set }`  

```csharp
private System.Int32 parkedCars { private get; private set; }
```

- `private System.Int32 parkingCapacity { private get; private set }`  

```csharp
private System.Int32 parkingCapacity { private get; private set; }
```


## Constructors

- `public ParkingSection()`  

```csharp
public ParkingSection();
```


## Methods

- `private CheckParkingLanes(Unity.Entities.DynamicBuffer<Game.Objects.SubObject> subObjects, System.Int32& laneCount) : System.Void`  

```csharp
private System.Void CheckParkingLanes(Unity.Entities.DynamicBuffer<Game.Objects.SubObject> subObjects, System.Int32& laneCount);
```

- `private CheckParkingLanes(Unity.Entities.DynamicBuffer<Game.Net.SubNet> subNets, System.Int32& laneCount) : System.Void`  

```csharp
private System.Void CheckParkingLanes(Unity.Entities.DynamicBuffer<Game.Net.SubNet> subNets, System.Int32& laneCount);
```

- `private CheckParkingLanes(Unity.Entities.DynamicBuffer<Game.Net.SubLane> subLanes, System.Int32& laneCount) : System.Void`  

```csharp
private System.Void CheckParkingLanes(Unity.Entities.DynamicBuffer<Game.Net.SubLane> subLanes, System.Int32& laneCount);
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


