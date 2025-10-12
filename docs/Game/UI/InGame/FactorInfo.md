# Game.UI.InGame.FactorInfo

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IComparable<Game.UI.InGame.FactorInfo>`  

**Attributes:** `IsReadOnly`  

## Fields

- `private readonly System.Int32 <factor>k__BackingField`  
- `private readonly System.Int32 <weight>k__BackingField`  

## Properties

- `public System.Int32 factor { get }`  
- `public System.Int32 weight { get }`  

## Constructors

- `public FactorInfo(System.Int32 factor, System.Int32 weight)`  

## Methods

- `public CompareTo(Game.UI.InGame.FactorInfo other) : System.Int32`  
- `public static FromFactorArray(Unity.Collections.NativeArray<System.Int32> factors, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Game.UI.InGame.FactorInfo>`  
- `public WriteBuildingHappinessFactor(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `public WriteDemandFactor(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `public WriteHappinessFactor(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

