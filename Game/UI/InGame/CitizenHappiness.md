# Game.UI.InGame.CitizenHappiness

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `IsReadOnly`  

## Code

```csharp
public sealed struct CitizenHappiness : Colossal.UI.Binding.IJsonWritable
{
    private readonly Game.UI.InGame.CitizenHappinessKey <key>k__BackingField;
    private static readonly System.String[] kHappinessPaths;

    private Game.UI.InGame.CitizenHappinessKey key { private get; }

    public CitizenHappiness(Game.UI.InGame.CitizenHappinessKey key);

    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private readonly Game.UI.InGame.CitizenHappinessKey <key>k__BackingField`  

```csharp
private readonly Game.UI.InGame.CitizenHappinessKey <key>k__BackingField;
```

- `private static readonly System.String[] kHappinessPaths`  

```csharp
private static readonly System.String[] kHappinessPaths;
```


## Properties

- `private Game.UI.InGame.CitizenHappinessKey key { private get }`  

```csharp
private Game.UI.InGame.CitizenHappinessKey key { private get; }
```


## Constructors

- `public CitizenHappiness(Game.UI.InGame.CitizenHappinessKey key)`  

```csharp
public CitizenHappiness(CitizenHappinessKey key)
	{
		this.key = key;
	}
```


## Methods

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public void Write(IJsonWriter writer)
	{
		writer.TypeBegin(typeof(CitizenHappiness).FullName);
		writer.PropertyName("key");
		writer.Write(Enum.GetName(typeof(CitizenHappinessKey), key));
		writer.PropertyName("iconPath");
		writer.Write(kHappinessPaths[(int)key]);
		writer.TypeEnd();
	}
```


