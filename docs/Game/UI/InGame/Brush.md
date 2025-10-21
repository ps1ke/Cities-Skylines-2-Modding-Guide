# Game.UI.InGame.ToolUISystem+Brush

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public sealed struct Brush : Colossal.UI.Binding.IJsonWritable
{
    public Unity.Entities.Entity m_Entity;
    public System.String m_Name;
    public System.String m_Icon;
    public System.Int32 m_Priority;

    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Entity`  

```csharp
public Unity.Entities.Entity m_Entity;
```

- `public System.String m_Name`  

```csharp
public System.String m_Name;
```

- `public System.String m_Icon`  

```csharp
public System.String m_Icon;
```

- `public System.Int32 m_Priority`  

```csharp
public System.Int32 m_Priority;
```


## Methods

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


