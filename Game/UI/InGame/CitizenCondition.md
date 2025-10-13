# Game.UI.InGame.CitizenCondition

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`, `System.IComparable<Game.UI.InGame.CitizenCondition>`  

**Attributes:** `IsReadOnly`  

## Code

```csharp
public sealed struct CitizenCondition : Colossal.UI.Binding.IJsonWritable, System.IComparable<Game.UI.InGame.CitizenCondition>
{
    private readonly Game.UI.InGame.CitizenConditionKey <key>k__BackingField;
    private static readonly System.String[] kConditionPaths;

    private Game.UI.InGame.CitizenConditionKey key { private get; }

    public CitizenCondition(Game.UI.InGame.CitizenConditionKey key);

    public System.Int32 CompareTo(Game.UI.InGame.CitizenCondition other);
    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private readonly Game.UI.InGame.CitizenConditionKey <key>k__BackingField`  

```csharp
private readonly Game.UI.InGame.CitizenConditionKey <key>k__BackingField;
```

- `private static readonly System.String[] kConditionPaths`  

```csharp
private static readonly System.String[] kConditionPaths;
```


## Properties

- `private Game.UI.InGame.CitizenConditionKey key { private get }`  

```csharp
private Game.UI.InGame.CitizenConditionKey key { private get; }
```


## Constructors

- `public CitizenCondition(Game.UI.InGame.CitizenConditionKey key)`  

```csharp
public CitizenCondition(CitizenConditionKey key)
	{
		this.key = key;
	}
```


## Methods

- `public CompareTo(Game.UI.InGame.CitizenCondition other) : System.Int32`  

```csharp
public int CompareTo(CitizenCondition other)
	{
		return key.CompareTo(other.key);
	}
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public void Write(IJsonWriter writer)
	{
		writer.TypeBegin(typeof(CitizenCondition).FullName);
		writer.PropertyName("key");
		writer.Write(Enum.GetName(typeof(CitizenConditionKey), key));
		writer.PropertyName("iconPath");
		writer.Write(kConditionPaths[(int)key]);
		writer.TypeEnd();
	}
```


