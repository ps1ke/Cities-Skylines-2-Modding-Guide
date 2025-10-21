# Game.UI.InGame.HouseholdSidebarSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class HouseholdSidebarSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Unity.Entities.Entity <residenceEntity>k__BackingField;
    private Game.UI.InGame.HouseholdSidebarSection+HouseholdResult <household>k__BackingField;
    private Game.UI.InGame.HouseholdSidebarSection+HouseholdSidebarVariant <variant>k__BackingField;
    private System.Boolean <residenceIsHomelessShelter>k__BackingField;
    private Unity.Collections.NativeArray<System.Int32> m_Results;
    private Unity.Collections.NativeArray<Unity.Entities.Entity> m_ResidenceResult;
    private Unity.Collections.NativeArray<Game.UI.InGame.HouseholdSidebarSection+HouseholdResult> m_HouseholdResult;
    private Unity.Collections.NativeList<Game.UI.InGame.HouseholdSidebarSection+ResidentResult> m_ResidentsResult;
    private Unity.Collections.NativeList<Unity.Entities.Entity> m_PetsResult;
    private Unity.Collections.NativeList<Game.UI.InGame.HouseholdSidebarSection+HouseholdResult> m_HouseholdsResult;
    private Colossal.UI.Binding.RawMapBinding<System.Int32> m_HouseholdMap;
    private Colossal.UI.Binding.RawMapBinding<System.Int32> m_ResidentMap;
    private Colossal.UI.Binding.RawMapBinding<System.Int32> m_PetMap;
    private Game.UI.InGame.HouseholdSidebarSection+TypeHandle __TypeHandle;
    private static const System.String kHouseholdIcon;
    private static const System.String kResidenceIcon;
    private static const System.String kHomelessShelterIcon;
    private static const System.String kPetIcon;
    private static const System.String kItemType;

    protected System.String group { protected get; }
    protected System.Boolean displayForDestroyedObjects { protected get; }
    protected System.Boolean displayForUnderConstruction { protected get; }
    private Unity.Entities.Entity residenceEntity { private get; private set; }
    private Game.UI.InGame.HouseholdSidebarSection+HouseholdResult household { private get; private set; }
    private Game.UI.InGame.HouseholdSidebarSection+HouseholdSidebarVariant variant { private get; private set; }
    private System.Boolean residenceIsHomelessShelter { private get; private set; }

    public HouseholdSidebarSection();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void BindHousehold(Colossal.UI.Binding.IJsonWriter writer, System.Int32 index);
    private System.Void BindPet(Colossal.UI.Binding.IJsonWriter writer, System.Int32 index);
    private System.Void BindResident(Colossal.UI.Binding.IJsonWriter writer, System.Int32 index);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Void WriteItem(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity, System.String iconPath, System.Int32 memberCount);
}
```


## Fields

- `private Unity.Entities.Entity <residenceEntity>k__BackingField`  

```csharp
private Unity.Entities.Entity <residenceEntity>k__BackingField;
```

- `private Game.UI.InGame.HouseholdSidebarSection+HouseholdResult <household>k__BackingField`  

```csharp
private Game.UI.InGame.HouseholdSidebarSection+HouseholdResult <household>k__BackingField;
```

- `private Game.UI.InGame.HouseholdSidebarSection+HouseholdSidebarVariant <variant>k__BackingField`  

```csharp
private Game.UI.InGame.HouseholdSidebarSection+HouseholdSidebarVariant <variant>k__BackingField;
```

- `private System.Boolean <residenceIsHomelessShelter>k__BackingField`  

```csharp
private System.Boolean <residenceIsHomelessShelter>k__BackingField;
```

- `private Unity.Collections.NativeArray<System.Int32> m_Results`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_Results;
```

- `private Unity.Collections.NativeArray<Unity.Entities.Entity> m_ResidenceResult`  

```csharp
private Unity.Collections.NativeArray<Unity.Entities.Entity> m_ResidenceResult;
```

- `private Unity.Collections.NativeArray<Game.UI.InGame.HouseholdSidebarSection+HouseholdResult> m_HouseholdResult`  

```csharp
private Unity.Collections.NativeArray<Game.UI.InGame.HouseholdSidebarSection+HouseholdResult> m_HouseholdResult;
```

- `private Unity.Collections.NativeList<Game.UI.InGame.HouseholdSidebarSection+ResidentResult> m_ResidentsResult`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.HouseholdSidebarSection+ResidentResult> m_ResidentsResult;
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> m_PetsResult`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> m_PetsResult;
```

- `private Unity.Collections.NativeList<Game.UI.InGame.HouseholdSidebarSection+HouseholdResult> m_HouseholdsResult`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.HouseholdSidebarSection+HouseholdResult> m_HouseholdsResult;
```

- `private Colossal.UI.Binding.RawMapBinding<System.Int32> m_HouseholdMap`  

```csharp
private Colossal.UI.Binding.RawMapBinding<System.Int32> m_HouseholdMap;
```

- `private Colossal.UI.Binding.RawMapBinding<System.Int32> m_ResidentMap`  

```csharp
private Colossal.UI.Binding.RawMapBinding<System.Int32> m_ResidentMap;
```

- `private Colossal.UI.Binding.RawMapBinding<System.Int32> m_PetMap`  

```csharp
private Colossal.UI.Binding.RawMapBinding<System.Int32> m_PetMap;
```

- `private Game.UI.InGame.HouseholdSidebarSection+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.HouseholdSidebarSection+TypeHandle __TypeHandle;
```

- `private static const System.String kHouseholdIcon`  

```csharp
private static const System.String kHouseholdIcon;
```

- `private static const System.String kResidenceIcon`  

```csharp
private static const System.String kResidenceIcon;
```

- `private static const System.String kHomelessShelterIcon`  

```csharp
private static const System.String kHomelessShelterIcon;
```

- `private static const System.String kPetIcon`  

```csharp
private static const System.String kPetIcon;
```

- `private static const System.String kItemType`  

```csharp
private static const System.String kItemType;
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

- `protected System.Boolean displayForUnderConstruction { protected get }`  

```csharp
protected System.Boolean displayForUnderConstruction { protected get; }
```

- `private Unity.Entities.Entity residenceEntity { private get; private set }`  

```csharp
private Unity.Entities.Entity residenceEntity { private get; private set; }
```

- `private Game.UI.InGame.HouseholdSidebarSection+HouseholdResult household { private get; private set }`  

```csharp
private Game.UI.InGame.HouseholdSidebarSection+HouseholdResult household { private get; private set; }
```

- `private Game.UI.InGame.HouseholdSidebarSection+HouseholdSidebarVariant variant { private get; private set }`  

```csharp
private Game.UI.InGame.HouseholdSidebarSection+HouseholdSidebarVariant variant { private get; private set; }
```

- `private System.Boolean residenceIsHomelessShelter { private get; private set }`  

```csharp
private System.Boolean residenceIsHomelessShelter { private get; private set; }
```


## Constructors

- `public HouseholdSidebarSection()`  

```csharp
public HouseholdSidebarSection();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private BindHousehold(Colossal.UI.Binding.IJsonWriter writer, System.Int32 index) : System.Void`  

```csharp
private System.Void BindHousehold(Colossal.UI.Binding.IJsonWriter writer, System.Int32 index);
```

- `private BindPet(Colossal.UI.Binding.IJsonWriter writer, System.Int32 index) : System.Void`  

```csharp
private System.Void BindPet(Colossal.UI.Binding.IJsonWriter writer, System.Int32 index);
```

- `private BindResident(Colossal.UI.Binding.IJsonWriter writer, System.Int32 index) : System.Void`  

```csharp
private System.Void BindResident(Colossal.UI.Binding.IJsonWriter writer, System.Int32 index);
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

- `private WriteItem(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity, System.String iconPath, System.Int32 memberCount = 0) : System.Void`  

```csharp
private System.Void WriteItem(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity, System.String iconPath, System.Int32 memberCount);
```


## Nested types

- `Game.UI.InGame.HouseholdSidebarSection+Result`  
- `Game.UI.InGame.HouseholdSidebarSection+HouseholdSidebarVariant`  
- `Game.UI.InGame.HouseholdSidebarSection+CheckVisibilityJob`  
- `Game.UI.InGame.HouseholdSidebarSection+CollectDataJob`  
- `Game.UI.InGame.HouseholdSidebarSection+HouseholdResult`  
- `Game.UI.InGame.HouseholdSidebarSection+HouseholdComparer`  
- `Game.UI.InGame.HouseholdSidebarSection+ResidentResult`  
- `Game.UI.InGame.HouseholdSidebarSection+ResidentComparer`  
- `Game.UI.InGame.HouseholdSidebarSection+TypeHandle`  

