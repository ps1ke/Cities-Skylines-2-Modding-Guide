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
public FactorInfo(int factor, int weight)
	{
		this.factor = factor;
		this.weight = weight;
	}
```


## Methods

- `public CompareTo(Game.UI.InGame.FactorInfo other) : System.Int32`  

```csharp
public int CompareTo(FactorInfo other)
	{
		int num = math.abs(other.weight).CompareTo(math.abs(weight));
		if (num == 0)
		{
			return other.factor.CompareTo(factor);
		}
		return num;
	}
```

- `public static FromFactorArray(Unity.Collections.NativeArray<System.Int32> factors, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Game.UI.InGame.FactorInfo>`  

```csharp
public static NativeList<FactorInfo> FromFactorArray(NativeArray<int> factors, Allocator allocator)
	{
		NativeList<FactorInfo> nativeList = new NativeList<FactorInfo>(factors.Length, allocator);
		for (int i = 0; i < factors.Length; i++)
		{
			if (factors[i] != 0)
			{
				nativeList.Add(new FactorInfo(i, factors[i]));
			}
		}
		nativeList.Sort();
		return nativeList;
	}
```

- `public WriteBuildingHappinessFactor(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public void WriteBuildingHappinessFactor(IJsonWriter writer)
	{
		writer.TypeBegin(GetType().FullName);
		writer.PropertyName("factor");
		writer.Write(Enum.GetName(typeof(BuildingHappinessFactor), factor));
		writer.PropertyName("weight");
		writer.Write(weight);
		writer.TypeEnd();
	}
```

- `public WriteDemandFactor(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public void WriteDemandFactor(IJsonWriter writer)
	{
		writer.TypeBegin(GetType().FullName);
		writer.PropertyName("factor");
		writer.Write(Enum.GetName(typeof(DemandFactor), factor));
		writer.PropertyName("weight");
		writer.Write(weight);
		writer.TypeEnd();
	}
```

- `public WriteHappinessFactor(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public void WriteHappinessFactor(IJsonWriter writer)
	{
		writer.TypeBegin(GetType().FullName);
		writer.PropertyName("factor");
		writer.Write(Enum.GetName(typeof(CitizenHappinessSystem.HappinessFactor), factor));
		writer.PropertyName("weight");
		writer.Write(weight);
		writer.TypeEnd();
	}
```


