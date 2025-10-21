# Game.Audio.Radio.Radio+RadioChannel

**Assembly:** `Game`  
**Namespace:** `Game.Audio.Radio`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.Assets.IContentPrerequisite`  

## Code

```csharp
public class RadioChannel : Game.Assets.IContentPrerequisite
{
    public System.String name;
    public System.String nameId;
    public System.String description;
    public System.String icon;
    public System.Int32 uiPriority;
    public System.String network;
    public Game.Audio.Radio.Radio+Program[] programs;
    private System.String[] <contentPrerequisites>k__BackingField;

    public System.String[] contentPrerequisites { get; set; }

    public RadioChannel();

    public Game.Audio.Radio.Radio+RuntimeRadioChannel CreateRuntime(System.String path);
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

- `public System.String icon`  

```csharp
public System.String icon;
```

- `public System.Int32 uiPriority`  

```csharp
public System.Int32 uiPriority;
```

- `public System.String network`  

```csharp
public System.String network;
```

- `public Game.Audio.Radio.Radio+Program[] programs`  

```csharp
public Game.Audio.Radio.Radio+Program[] programs;
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

- `public RadioChannel()`  

```csharp
public RadioChannel();
```


## Methods

- `public CreateRuntime(System.String path) : Game.Audio.Radio.Radio+RuntimeRadioChannel`  

```csharp
public Game.Audio.Radio.Radio+RuntimeRadioChannel CreateRuntime(System.String path);
```


