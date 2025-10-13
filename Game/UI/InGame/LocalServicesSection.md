# Game.UI.InGame.LocalServicesSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LocalServicesSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.UI.ImageSystem m_ImageSystem;
    private Unity.Entities.EntityQuery m_ServiceDistrictBuildingQuery;
    private Unity.Collections.NativeList<Unity.Entities.Entity> <localServiceBuildings>k__BackingField;
    private Unity.Collections.NativeList<Unity.Entities.Entity> <prefabs>k__BackingField;

    protected System.String group { protected get; }
    private Unity.Collections.NativeList<Unity.Entities.Entity> localServiceBuildings { private get; private set; }
    private Unity.Collections.NativeList<Unity.Entities.Entity> prefabs { private get; private set; }

    public LocalServicesSection();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
}
```


## Fields

- `private Game.UI.ImageSystem m_ImageSystem`  

```csharp
private Game.UI.ImageSystem m_ImageSystem;
```

- `private Unity.Entities.EntityQuery m_ServiceDistrictBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_ServiceDistrictBuildingQuery;
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> <localServiceBuildings>k__BackingField`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> <localServiceBuildings>k__BackingField;
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> <prefabs>k__BackingField`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> <prefabs>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> localServiceBuildings { private get; private set }`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> localServiceBuildings { private get; private set; }
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> prefabs { private get; private set }`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> prefabs { private get; private set; }
```


## Constructors

- `public LocalServicesSection()`  

```csharp
public LocalServicesSection();
```


## Methods

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


