# Game.UI.InGame.DispatchedVehiclesSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DispatchedVehiclesSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Unity.Entities.EntityQuery m_ServiceDispatchQuery;
    private Unity.Collections.NativeList<Unity.Entities.Entity> m_VehiclesResult;
    private Unity.Collections.NativeList<Game.UI.InGame.VehiclesSection+UIVehicle> <vehicleList>k__BackingField;
    private Game.UI.InGame.DispatchedVehiclesSection+TypeHandle __TypeHandle;

    protected System.String group { protected get; }
    protected System.Boolean displayForDestroyedObjects { protected get; }
    protected System.Boolean displayForUpgrades { protected get; }
    private Unity.Collections.NativeList<Game.UI.InGame.VehiclesSection+UIVehicle> vehicleList { private get; private set; }

    public DispatchedVehiclesSection();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_ServiceDispatchQuery`  

```csharp
private Unity.Entities.EntityQuery m_ServiceDispatchQuery;
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> m_VehiclesResult`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> m_VehiclesResult;
```

- `private Unity.Collections.NativeList<Game.UI.InGame.VehiclesSection+UIVehicle> <vehicleList>k__BackingField`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.VehiclesSection+UIVehicle> <vehicleList>k__BackingField;
```

- `private Game.UI.InGame.DispatchedVehiclesSection+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.DispatchedVehiclesSection+TypeHandle __TypeHandle;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `protected System.Boolean displayForDestroyedObjects { protected get }`  

```csharp
protected System.Boolean displayForDestroyedObjects { protected get; }
```

- `protected System.Boolean displayForUpgrades { protected get }`  

```csharp
protected System.Boolean displayForUpgrades { protected get; }
```

- `private Unity.Collections.NativeList<Game.UI.InGame.VehiclesSection+UIVehicle> vehicleList { private get; private set }`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.VehiclesSection+UIVehicle> vehicleList { private get; private set; }
```


## Constructors

- `public DispatchedVehiclesSection()`  

```csharp
public DispatchedVehiclesSection();
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

- `Game.UI.InGame.DispatchedVehiclesSection+CollectDispatchedVehiclesJob`  
- `Game.UI.InGame.DispatchedVehiclesSection+TypeHandle`  

