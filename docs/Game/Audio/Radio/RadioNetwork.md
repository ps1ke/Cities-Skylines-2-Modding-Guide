# Game.Audio.Radio.Radio+RadioNetwork

**Assembly:** `Game`  
**Namespace:** `Game.Audio.Radio`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IComparable<Game.Audio.Radio.Radio+RadioNetwork>`, `Colossal.UI.Binding.IJsonWritable`, `Game.Assets.IContentPrerequisite`  

## Code

```csharp
public class RadioNetwork : System.IComparable<Game.Audio.Radio.Radio+RadioNetwork>, Colossal.UI.Binding.IJsonWritable, Game.Assets.IContentPrerequisite
{
    public System.String name;
    public System.String nameId;
    public System.String description;
    public System.String descriptionId;
    public System.String icon;
    public System.Boolean allowAds;
    public System.Int32 uiPriority;
    private System.String[] <contentPrerequisites>k__BackingField;

    public System.String[] contentPrerequisites { get; set; }

    public RadioNetwork();

    public System.Int32 CompareTo(Game.Audio.Radio.Radio+RadioNetwork other);
    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `public System.String name`  

```csharp
public System.String name;
```

- `public System.String nameId`  

```csharp
public System.String nameId;
```

- `public System.String description`  

```csharp
public System.String description;
```

- `public System.String descriptionId`  

```csharp
public System.String descriptionId;
```

- `public System.String icon`  

```csharp
public System.String icon;
```

- `public System.Boolean allowAds`  

```csharp
public System.Boolean allowAds;
```

- `public System.Int32 uiPriority`  

```csharp
public System.Int32 uiPriority;
```

- `private System.String[] <contentPrerequisites>k__BackingField`  

```csharp
private System.String[] <contentPrerequisites>k__BackingField;
```


## Properties

- `public System.String[] contentPrerequisites { get; set }`  

```csharp
public System.String[] contentPrerequisites { get; set; }
```


## Constructors

- `public RadioNetwork()`  

```csharp
public RadioNetwork();
```


## Methods

- `public CompareTo(Game.Audio.Radio.Radio+RadioNetwork other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Game.Audio.Radio.Radio+RadioNetwork other);
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


