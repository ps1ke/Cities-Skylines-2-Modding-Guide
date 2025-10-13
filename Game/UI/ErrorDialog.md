# Game.UI.ErrorDialog

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public class ErrorDialog : Colossal.UI.Binding.IJsonWritable
{
    public Game.UI.ErrorDialog+Severity severity;
    public Game.UI.ErrorDialog+Actions actions;
    public Game.UI.Localization.LocalizedString localizedTitle;
    public Game.UI.Localization.LocalizedString localizedMessage;
    public System.String errorDetails;

    public ErrorDialog();

    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `public Game.UI.ErrorDialog+Severity severity`  

```csharp
public Game.UI.ErrorDialog+Severity severity;
```

- `public Game.UI.ErrorDialog+Actions actions`  

```csharp
public Game.UI.ErrorDialog+Actions actions;
```

- `public Game.UI.Localization.LocalizedString localizedTitle`  

```csharp
public Game.UI.Localization.LocalizedString localizedTitle;
```

- `public Game.UI.Localization.LocalizedString localizedMessage`  

```csharp
public Game.UI.Localization.LocalizedString localizedMessage;
```

- `public System.String errorDetails`  

```csharp
public System.String errorDetails;
```


## Constructors

- `public ErrorDialog()`  

```csharp
public ErrorDialog();
```


## Methods

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public void Write(IJsonWriter writer)
	{
		writer.TypeBegin(GetType().FullName);
		writer.PropertyName("severity");
		writer.Write((int)severity);
		writer.PropertyName("actions");
		writer.Write((int)actions);
		writer.PropertyName("localizedTitle");
		writer.Write(localizedTitle);
		writer.PropertyName("localizedMessage");
		writer.Write(localizedMessage);
		writer.PropertyName("errorDetails");
		writer.Write(errorDetails);
		writer.TypeEnd();
	}
```


## Nested types

- `Game.UI.ErrorDialog+Severity`  
- `Game.UI.ErrorDialog+Actions`  

