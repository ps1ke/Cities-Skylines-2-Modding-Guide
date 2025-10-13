# Game.UI.InGame.TaxResource

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonReadable`, `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public sealed struct TaxResource : Colossal.UI.Binding.IJsonReadable, Colossal.UI.Binding.IJsonWritable
{
    public System.Int32 m_Resource;
    public System.Int32 m_AreaType;

    public System.Void Read(Colossal.UI.Binding.IJsonReader reader);
    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `public System.Int32 m_Resource`  

```csharp
public System.Int32 m_Resource;
```

- `public System.Int32 m_AreaType`  

```csharp
public System.Int32 m_AreaType;
```


## Methods

- `public Read(Colossal.UI.Binding.IJsonReader reader) : System.Void`  

```csharp
public void Read(IJsonReader reader)
	{
		reader.ReadMapBegin();
		reader.ReadProperty("resource");
		reader.Read(out m_Resource);
		reader.ReadProperty("area");
		reader.Read(out m_AreaType);
		reader.ReadMapEnd();
	}
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public void Write(IJsonWriter writer)
	{
		writer.TypeBegin(GetType().FullName);
		writer.PropertyName("resource");
		writer.Write(m_Resource);
		writer.PropertyName("area");
		writer.Write(m_AreaType);
		writer.TypeEnd();
	}
```


