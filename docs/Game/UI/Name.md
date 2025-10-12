# Game.UI.NameSystem+Name

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `private Game.UI.NameSystem+NameType m_NameType`  
- `private System.String m_NameID`  
- `private System.String[] m_NameArgs`  

## Methods

- `private BindCustomName(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `private BindFormattedName(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `private BindLocalizedName(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `public static CustomName(System.String name) : Game.UI.NameSystem+Name`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public static FormattedName(System.String nameID, System.String[] args) : Game.UI.NameSystem+Name`  
- `public static LocalizedName(System.String nameID) : Game.UI.NameSystem+Name`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

