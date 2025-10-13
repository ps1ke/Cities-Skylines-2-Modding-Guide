# Game.UI.InGame.SelectVehiclesSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SelectVehiclesSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
    private Game.UI.ImageSystem m_ImageSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Prefabs.TransportVehicleSelectData m_TransportVehicleSelectData;
    private Unity.Entities.EntityQuery m_VehiclePrefabQuery;
    private Unity.Entities.EntityQuery m_DepotQuery;
    private Unity.Entities.Entity <primaryVehicle>k__BackingField;
    private Unity.Entities.Entity <secondaryVehicle>k__BackingField;
    private Unity.Collections.NativeList<Unity.Entities.Entity> <primaryVehicles>k__BackingField;
    private Unity.Collections.NativeList<Unity.Entities.Entity> <secondaryVehicles>k__BackingField;
    private Unity.Collections.NativeArray<System.Int32> m_Results;
    private Game.UI.InGame.SelectVehiclesSection+TypeHandle __TypeHandle;

    protected System.String group { protected get; }
    private Unity.Entities.Entity primaryVehicle { private get; private set; }
    private Unity.Entities.Entity secondaryVehicle { private get; private set; }
    private Unity.Collections.NativeList<Unity.Entities.Entity> primaryVehicles { private get; private set; }
    private Unity.Collections.NativeList<Unity.Entities.Entity> secondaryVehicles { private get; private set; }

    public SelectVehiclesSection();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Void SetVehicleModel(Unity.Entities.Entity primary, Unity.Entities.Entity secondary);
    private System.Boolean Visible();
    private System.Void WriteVehicle(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity);
}
```


## Fields

- `private Game.UI.InGame.PrefabUISystem m_PrefabUISystem`  

```csharp
private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
```

- `private Game.UI.ImageSystem m_ImageSystem`  

```csharp
private Game.UI.ImageSystem m_ImageSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Prefabs.TransportVehicleSelectData m_TransportVehicleSelectData`  

```csharp
private Game.Prefabs.TransportVehicleSelectData m_TransportVehicleSelectData;
```

- `private Unity.Entities.EntityQuery m_VehiclePrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_VehiclePrefabQuery;
```

- `private Unity.Entities.EntityQuery m_DepotQuery`  

```csharp
private Unity.Entities.EntityQuery m_DepotQuery;
```

- `private Unity.Entities.Entity <primaryVehicle>k__BackingField`  

```csharp
private Unity.Entities.Entity <primaryVehicle>k__BackingField;
```

- `private Unity.Entities.Entity <secondaryVehicle>k__BackingField`  

```csharp
private Unity.Entities.Entity <secondaryVehicle>k__BackingField;
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> <primaryVehicles>k__BackingField`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> <primaryVehicles>k__BackingField;
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> <secondaryVehicles>k__BackingField`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> <secondaryVehicles>k__BackingField;
```

- `private Unity.Collections.NativeArray<System.Int32> m_Results`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_Results;
```

- `private Game.UI.InGame.SelectVehiclesSection+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.SelectVehiclesSection+TypeHandle __TypeHandle;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private Unity.Entities.Entity primaryVehicle { private get; private set }`  

```csharp
private Unity.Entities.Entity primaryVehicle { private get; private set; }
```

- `private Unity.Entities.Entity secondaryVehicle { private get; private set }`  

```csharp
private Unity.Entities.Entity secondaryVehicle { private get; private set; }
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> primaryVehicles { private get; private set }`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> primaryVehicles { private get; private set; }
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> secondaryVehicles { private get; private set }`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> secondaryVehicles { private get; private set; }
```


## Constructors

- `public SelectVehiclesSection()`  

```csharp
public SelectVehiclesSection();
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

- `private SetVehicleModel(Unity.Entities.Entity primary, Unity.Entities.Entity secondary) : System.Void`  

```csharp
private System.Void SetVehicleModel(Unity.Entities.Entity primary, Unity.Entities.Entity secondary);
```

- `private Visible() : System.Boolean`  

```csharp
private System.Boolean Visible();
```

- `private WriteVehicle(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void WriteVehicle(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity);
```


## Nested types

- `Game.UI.InGame.SelectVehiclesSection+Result`  
- `Game.UI.InGame.SelectVehiclesSection+DepotsJob`  
- `Game.UI.InGame.SelectVehiclesSection+VehiclesListJob`  
- `Game.UI.InGame.SelectVehiclesSection+TypeHandle`  

