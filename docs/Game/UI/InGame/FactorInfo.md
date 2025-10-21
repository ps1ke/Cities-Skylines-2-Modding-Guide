# Game.UI.InGame.FactorInfo

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IComparable<Game.UI.InGame.FactorInfo>`  

**Attributes:** `IsReadOnly`  

## Code

```csharp
public sealed struct FactorInfo : System.IComparable<Game.UI.InGame.FactorInfo>
{
    private readonly System.Int32 <factor>k__BackingField;
    private readonly System.Int32 <weight>k__BackingField;

    public System.Int32 factor { get; }
    public System.Int32 weight { get; }

    public FactorInfo(System.Int32 factor, System.Int32 weight);

    public System.Int32 CompareTo(Game.UI.InGame.FactorInfo other);
    public static Unity.Collections.NativeList<Game.UI.InGame.FactorInfo> FromFactorArray(Unity.Collections.NativeArray<System.Int32> factors, Unity.Collections.Allocator allocator);
    public System.Void WriteBuildingHappinessFactor(Colossal.UI.Binding.IJsonWriter writer);
    public System.Void WriteDemandFactor(Colossal.UI.Binding.IJsonWriter writer);
    public System.Void WriteHappinessFactor(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private readonly System.Int32 <factor>k__BackingField`  

```csharp
private readonly System.Int32 <factor>k__BackingField;
```

- `private readonly System.Int32 <weight>k__BackingField`  

```csharp
private readonly System.Int32 <weight>k__BackingField;
```


## Properties

- `public System.Int32 factor { get }`  

```csharp
public System.Int32 factor { get; }
```

- `public System.Int32 weight { get }`  

```csharp
public System.Int32 weight { get; }
```


## Constructors

- `public FactorInfo(System.Int32 factor, System.Int32 weight)`  

```csharp
public FactorInfo(System.Int32 factor, System.Int32 weight);
```


## Methods

- `public CompareTo(Game.UI.InGame.FactorInfo other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Game.UI.InGame.FactorInfo other);
```

- `public static FromFactorArray(Unity.Collections.NativeArray<System.Int32> factors, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Game.UI.InGame.FactorInfo>`  

```csharp
public static Unity.Collections.NativeList<Game.UI.InGame.FactorInfo> FromFactorArray(Unity.Collections.NativeArray<System.Int32> factors, Unity.Collections.Allocator allocator);
```

- `public WriteBuildingHappinessFactor(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void WriteBuildingHappinessFactor(Colossal.UI.Binding.IJsonWriter writer);
```

- `public WriteDemandFactor(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void WriteDemandFactor(Colossal.UI.Binding.IJsonWriter writer);
```

- `public WriteHappinessFactor(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void WriteHappinessFactor(Colossal.UI.Binding.IJsonWriter writer);
```


