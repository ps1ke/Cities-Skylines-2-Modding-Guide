# Game.UI.InGame.EmployeesSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private System.Int32 <employeeCount>k__BackingField`  
- `private System.Int32 <maxEmployees>k__BackingField`  
- `private Game.UI.InGame.EmploymentData <educationDataEmployees>k__BackingField`  
- `private Game.UI.InGame.EmploymentData <educationDataWorkplaces>k__BackingField`  
- `private Unity.Collections.NativeList<Unity.Entities.Entity> <districtBuildings>k__BackingField`  
- `private Unity.Entities.EntityQuery m_DistrictBuildingQuery`  

## Properties

- `protected System.String group { protected get }`  
- `private System.Int32 employeeCount { private get; private set }`  
- `private System.Int32 maxEmployees { private get; private set }`  
- `private Game.UI.InGame.EmploymentData educationDataEmployees { private get; private set }`  
- `private Game.UI.InGame.EmploymentData educationDataWorkplaces { private get; private set }`  
- `private Unity.Collections.NativeList<Unity.Entities.Entity> districtBuildings { private get; private set }`  

## Constructors

- `public EmployeesSection()`  

## Methods

- `private AddEmployees() : System.Void`  
- `private AddEmployees(Unity.Entities.Entity entity) : System.Void`  
- `private DisplayForDistrict() : System.Boolean`  
- `private GetEntity(Unity.Entities.Entity entity) : Unity.Entities.Entity`  
- `private HasEmployees(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnProcess() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `protected virtual Reset() : System.Void`  
- `private UpdateForDistricts() : System.Void`  
- `private Visible() : System.Boolean`  

