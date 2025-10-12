# Game.UI.InGame.HouseholdSidebarSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.Entity <residenceEntity>k__BackingField`  
- `private Game.UI.InGame.HouseholdSidebarSection+HouseholdResult <household>k__BackingField`  
- `private Game.UI.InGame.HouseholdSidebarSection+HouseholdSidebarVariant <variant>k__BackingField`  
- `private System.Boolean <residenceIsHomelessShelter>k__BackingField`  
- `private Unity.Collections.NativeArray<System.Int32> m_Results`  
- `private Unity.Collections.NativeArray<Unity.Entities.Entity> m_ResidenceResult`  
- `private Unity.Collections.NativeArray<Game.UI.InGame.HouseholdSidebarSection+HouseholdResult> m_HouseholdResult`  
- `private Unity.Collections.NativeList<Game.UI.InGame.HouseholdSidebarSection+ResidentResult> m_ResidentsResult`  
- `private Unity.Collections.NativeList<Unity.Entities.Entity> m_PetsResult`  
- `private Unity.Collections.NativeList<Game.UI.InGame.HouseholdSidebarSection+HouseholdResult> m_HouseholdsResult`  
- `private Colossal.UI.Binding.RawMapBinding<System.Int32> m_HouseholdMap`  
- `private Colossal.UI.Binding.RawMapBinding<System.Int32> m_ResidentMap`  
- `private Colossal.UI.Binding.RawMapBinding<System.Int32> m_PetMap`  
- `private Game.UI.InGame.HouseholdSidebarSection+TypeHandle __TypeHandle`  
- `private static const System.String kHouseholdIcon`  
- `private static const System.String kResidenceIcon`  
- `private static const System.String kHomelessShelterIcon`  
- `private static const System.String kPetIcon`  
- `private static const System.String kItemType`  

## Properties

- `protected System.String group { protected get }`  
- `protected System.Boolean displayForDestroyedObjects { protected get }`  
- `protected System.Boolean displayForUnderConstruction { protected get }`  
- `private Unity.Entities.Entity residenceEntity { private get; private set }`  
- `private Game.UI.InGame.HouseholdSidebarSection+HouseholdResult household { private get; private set }`  
- `private Game.UI.InGame.HouseholdSidebarSection+HouseholdSidebarVariant variant { private get; private set }`  
- `private System.Boolean residenceIsHomelessShelter { private get; private set }`  

## Constructors

- `public HouseholdSidebarSection()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private BindHousehold(Colossal.UI.Binding.IJsonWriter writer, System.Int32 index) : System.Void`  
- `private BindPet(Colossal.UI.Binding.IJsonWriter writer, System.Int32 index) : System.Void`  
- `private BindResident(Colossal.UI.Binding.IJsonWriter writer, System.Int32 index) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnProcess() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `protected virtual Reset() : System.Void`  
- `private WriteItem(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity, System.String iconPath, System.Int32 memberCount = 0) : System.Void`  

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

