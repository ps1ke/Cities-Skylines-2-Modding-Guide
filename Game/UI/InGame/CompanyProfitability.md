# Game.UI.InGame.CompanyProfitability

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `IsReadOnly`  

## Code

```csharp
public sealed struct CompanyProfitability : Colossal.UI.Binding.IJsonWritable
{
    private readonly Game.UI.InGame.CompanyProfitabilityKey <key>k__BackingField;
    private static readonly System.String[] kHappinessPaths;

    private Game.UI.InGame.CompanyProfitabilityKey key { private get; }

    public CompanyProfitability(System.Int32 profit);
    public CompanyProfitability(Game.UI.InGame.CompanyProfitabilityKey key);

    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private readonly Game.UI.InGame.CompanyProfitabilityKey <key>k__BackingField`  

```csharp
private readonly Game.UI.InGame.CompanyProfitabilityKey <key>k__BackingField;
```

- `private static readonly System.String[] kHappinessPaths`  

```csharp
private static readonly System.String[] kHappinessPaths;
```


## Properties

- `private Game.UI.InGame.CompanyProfitabilityKey key { private get }`  

```csharp
private Game.UI.InGame.CompanyProfitabilityKey key { private get; }
```


## Constructors

- `public CompanyProfitability(System.Int32 profit)`  

```csharp
public CompanyProfitability(CompanyProfitabilityKey key)
	{
		this.key = key;
	}
```

- `public CompanyProfitability(Game.UI.InGame.CompanyProfitabilityKey key)`  

```csharp
public CompanyProfitability(CompanyProfitabilityKey key)
	{
		this.key = key;
	}
```


## Methods

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public void Write(IJsonWriter writer)
	{
		writer.TypeBegin(typeof(CompanyProfitability).FullName);
		writer.PropertyName("key");
		writer.Write(Enum.GetName(typeof(CompanyProfitabilityKey), key));
		writer.PropertyName("iconPath");
		writer.Write(kHappinessPaths[(int)key]);
		writer.TypeEnd();
	}
```


