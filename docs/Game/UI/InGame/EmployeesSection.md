# Game.UI.InGame.EmployeesSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class EmployeesSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Int32 <employeeCount>k__BackingField;
    private System.Int32 <maxEmployees>k__BackingField;
    private Game.UI.InGame.EmploymentData <educationDataEmployees>k__BackingField;
    private Game.UI.InGame.EmploymentData <educationDataWorkplaces>k__BackingField;
    private Unity.Collections.NativeList<Unity.Entities.Entity> <districtBuildings>k__BackingField;
    private Unity.Entities.EntityQuery m_DistrictBuildingQuery;

    protected System.String group { protected get; }
    private System.Int32 employeeCount { private get; private set; }
    private System.Int32 maxEmployees { private get; private set; }
    private Game.UI.InGame.EmploymentData educationDataEmployees { private get; private set; }
    private Game.UI.InGame.EmploymentData educationDataWorkplaces { private get; private set; }
    private Unity.Collections.NativeList<Unity.Entities.Entity> districtBuildings { private get; private set; }

    public EmployeesSection();

    private System.Void AddEmployees();
    private System.Void AddEmployees(Unity.Entities.Entity entity);
    private System.Boolean DisplayForDistrict();
    private Unity.Entities.Entity GetEntity(Unity.Entities.Entity entity);
    private System.Boolean HasEmployees(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Void UpdateForDistricts();
    private System.Boolean Visible();
}
```


## Fields

- `private System.Int32 <employeeCount>k__BackingField`  

```csharp
private System.Int32 <employeeCount>k__BackingField;
```

- `private System.Int32 <maxEmployees>k__BackingField`  

```csharp
private System.Int32 <maxEmployees>k__BackingField;
```

- `private Game.UI.InGame.EmploymentData <educationDataEmployees>k__BackingField`  

```csharp
private Game.UI.InGame.EmploymentData <educationDataEmployees>k__BackingField;
```

- `private Game.UI.InGame.EmploymentData <educationDataWorkplaces>k__BackingField`  

```csharp
private Game.UI.InGame.EmploymentData <educationDataWorkplaces>k__BackingField;
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> <districtBuildings>k__BackingField`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> <districtBuildings>k__BackingField;
```

- `private Unity.Entities.EntityQuery m_DistrictBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_DistrictBuildingQuery;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Int32 employeeCount { private get; private set }`  

```csharp
private System.Int32 employeeCount { private get; private set; }
```

- `private System.Int32 maxEmployees { private get; private set }`  

```csharp
private System.Int32 maxEmployees { private get; private set; }
```

- `private Game.UI.InGame.EmploymentData educationDataEmployees { private get; private set }`  

```csharp
private Game.UI.InGame.EmploymentData educationDataEmployees { private get; private set; }
```

- `private Game.UI.InGame.EmploymentData educationDataWorkplaces { private get; private set }`  

```csharp
private Game.UI.InGame.EmploymentData educationDataWorkplaces { private get; private set; }
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> districtBuildings { private get; private set }`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> districtBuildings { private get; private set; }
```


## Constructors

- `public EmployeesSection()`  

```csharp
public EmployeesSection();
```


## Methods

- `private AddEmployees() : System.Void`  

```csharp
private System.Void AddEmployees();
```

- `private AddEmployees(Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void AddEmployees(Unity.Entities.Entity entity);
```

- `private DisplayForDistrict() : System.Boolean`  

```csharp
private System.Boolean DisplayForDistrict();
```

- `private GetEntity(Unity.Entities.Entity entity) : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity GetEntity(Unity.Entities.Entity entity);
```

- `private HasEmployees(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasEmployees(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
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

- `private UpdateForDistricts() : System.Void`  

```csharp
private System.Void UpdateForDistricts();
```

- `private Visible() : System.Boolean`  

```csharp
private System.Boolean Visible();
```


