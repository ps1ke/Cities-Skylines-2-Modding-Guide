# Game.UI.Menu.NotificationUISystem+NotificationInfo

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public class NotificationInfo : Colossal.UI.Binding.IJsonWritable
{
    public readonly System.String id;
    public System.String thumbnail;
    public System.Nullable<Game.UI.Localization.LocalizedString> title;
    public System.Nullable<Game.UI.Localization.LocalizedString> text;
    public Colossal.PSI.Common.ProgressState progressState;
    public System.Int32 progress;
    public System.Action onClicked;

    public NotificationInfo(System.String id);

    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `public readonly System.String id`  

```csharp
public readonly System.String id;
```

- `public System.String thumbnail`  

```csharp
public System.String thumbnail;
```

- `public System.Nullable<Game.UI.Localization.LocalizedString> title`  

```csharp
public System.Nullable<Game.UI.Localization.LocalizedString> title;
```

- `public System.Nullable<Game.UI.Localization.LocalizedString> text`  

```csharp
public System.Nullable<Game.UI.Localization.LocalizedString> text;
```

- `public Colossal.PSI.Common.ProgressState progressState`  

```csharp
public Colossal.PSI.Common.ProgressState progressState;
```

- `public System.Int32 progress`  

```csharp
public System.Int32 progress;
```

- `public System.Action onClicked`  

```csharp
public System.Action onClicked;
```


## Constructors

- `public NotificationInfo(System.String id)`  

```csharp
public NotificationInfo(System.String id);
```


## Methods

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


