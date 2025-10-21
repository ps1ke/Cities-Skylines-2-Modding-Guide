# Game.UI.Editor.ListField+Item

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public sealed struct Item : Colossal.UI.Binding.IJsonWritable
{
    public System.String m_Label;
    public System.Boolean m_Removable;
    public System.Object m_Data;
    public System.String[] m_SubItems;

    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `public System.String m_Label`  

```csharp
public System.String m_Label;
```

- `public System.Boolean m_Removable`  

```csharp
public System.Boolean m_Removable;
```

- `public System.Object m_Data`  

```csharp
public System.Object m_Data;
```

- `public System.String[] m_SubItems`  

```csharp
public System.String[] m_SubItems;
```


## Methods

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


