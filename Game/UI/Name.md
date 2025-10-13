# Game.UI.NameSystem+Name

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct Name : Colossal.UI.Binding.IJsonWritable, Colossal.Serialization.Entities.ISerializable
{
    private Game.UI.NameSystem+NameType m_NameType;
    private System.String m_NameID;
    private System.String[] m_NameArgs;

    private System.Void BindCustomName(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void BindFormattedName(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void BindLocalizedName(Colossal.UI.Binding.IJsonWriter writer);
    public static Game.UI.NameSystem+Name CustomName(System.String name);
    public System.Void Deserialize<TReader>(TReader reader);
    public static Game.UI.NameSystem+Name FormattedName(System.String nameID, System.String[] args);
    public static Game.UI.NameSystem+Name LocalizedName(System.String nameID);
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private Game.UI.NameSystem+NameType m_NameType`  

```csharp
private Game.UI.NameSystem+NameType m_NameType;
```

- `private System.String m_NameID`  

```csharp
private System.String m_NameID;
```

- `private System.String[] m_NameArgs`  

```csharp
private System.String[] m_NameArgs;
```


## Methods

- `private BindCustomName(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void BindCustomName(Colossal.UI.Binding.IJsonWriter writer);
```

- `private BindFormattedName(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void BindFormattedName(Colossal.UI.Binding.IJsonWriter writer);
```

- `private BindLocalizedName(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void BindLocalizedName(Colossal.UI.Binding.IJsonWriter writer);
```

- `public static CustomName(System.String name) : Game.UI.NameSystem+Name`  

```csharp
public static Game.UI.NameSystem+Name CustomName(System.String name);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public static FormattedName(System.String nameID, System.String[] args) : Game.UI.NameSystem+Name`  

```csharp
public static Game.UI.NameSystem+Name FormattedName(System.String nameID, System.String[] args);
```

- `public static LocalizedName(System.String nameID) : Game.UI.NameSystem+Name`  

```csharp
public static Game.UI.NameSystem+Name LocalizedName(System.String nameID);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


