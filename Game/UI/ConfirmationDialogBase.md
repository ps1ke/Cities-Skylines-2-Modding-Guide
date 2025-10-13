# Game.UI.ConfirmationDialogBase

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public abstract class ConfirmationDialogBase : Colossal.UI.Binding.IJsonWritable
{
    private System.Nullable<Game.UI.Localization.LocalizedString> title;
    private Game.UI.Localization.LocalizedString message;
    private Game.UI.Localization.LocalizedString confirmAction;
    private System.Nullable<Game.UI.Localization.LocalizedString> cancelAction;
    private Game.UI.Localization.LocalizedString[] otherActions;
    private System.Nullable<Game.UI.Localization.LocalizedString> details;
    private System.Boolean copyButton;
    protected static const System.String kDefaultSkin;
    protected static const System.String kParadoxSkin;

    protected System.String skin { protected get; }
    protected System.Boolean dismissible { protected get; }

    protected ConfirmationDialogBase(System.Nullable<Game.UI.Localization.LocalizedString> title, Game.UI.Localization.LocalizedString message, System.Nullable<Game.UI.Localization.LocalizedString> details, System.Boolean copyButton, Game.UI.Localization.LocalizedString confirmAction, System.Nullable<Game.UI.Localization.LocalizedString> cancelAction, Game.UI.Localization.LocalizedString[] otherActions);

    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.Nullable<Game.UI.Localization.LocalizedString> title`  

```csharp
private System.Nullable<Game.UI.Localization.LocalizedString> title;
```

- `private Game.UI.Localization.LocalizedString message`  

```csharp
private Game.UI.Localization.LocalizedString message;
```

- `private Game.UI.Localization.LocalizedString confirmAction`  

```csharp
private Game.UI.Localization.LocalizedString confirmAction;
```

- `private System.Nullable<Game.UI.Localization.LocalizedString> cancelAction`  

```csharp
private System.Nullable<Game.UI.Localization.LocalizedString> cancelAction;
```

- `private Game.UI.Localization.LocalizedString[] otherActions`  

```csharp
private Game.UI.Localization.LocalizedString[] otherActions;
```

- `private System.Nullable<Game.UI.Localization.LocalizedString> details`  

```csharp
private System.Nullable<Game.UI.Localization.LocalizedString> details;
```

- `private System.Boolean copyButton`  

```csharp
private System.Boolean copyButton;
```

- `protected static const System.String kDefaultSkin`  

```csharp
protected static const System.String kDefaultSkin;
```

- `protected static const System.String kParadoxSkin`  

```csharp
protected static const System.String kParadoxSkin;
```


## Properties

- `protected System.String skin { protected get }`  

```csharp
protected System.String skin { protected get; }
```

- `protected System.Boolean dismissible { protected get }`  

```csharp
protected System.Boolean dismissible { protected get; }
```


## Constructors

- `protected ConfirmationDialogBase(System.Nullable<Game.UI.Localization.LocalizedString> title, Game.UI.Localization.LocalizedString message, System.Nullable<Game.UI.Localization.LocalizedString> details, System.Boolean copyButton, Game.UI.Localization.LocalizedString confirmAction, System.Nullable<Game.UI.Localization.LocalizedString> cancelAction, Game.UI.Localization.LocalizedString[] otherActions)`  

```csharp
protected ConfirmationDialogBase(LocalizedString? title, LocalizedString message, LocalizedString? details, bool copyButton, LocalizedString confirmAction, LocalizedString? cancelAction, [CanBeNull] params LocalizedString[] otherActions)
	{
		this.title = title;
		this.message = message;
		this.confirmAction = confirmAction;
		this.cancelAction = cancelAction;
		this.otherActions = otherActions;
		this.details = details;
		this.copyButton = copyButton;
	}
```


## Methods

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public void Write(IJsonWriter writer)
	{
		writer.TypeBegin(GetType().FullName);
		writer.PropertyName("dismissible");
		writer.Write(dismissible);
		writer.PropertyName("skin");
		writer.Write(skin);
		writer.PropertyName("title");
		writer.Write(title);
		writer.PropertyName("message");
		writer.Write(message);
		writer.PropertyName("confirmAction");
		writer.Write(confirmAction);
		writer.PropertyName("cancelAction");
		writer.Write(cancelAction);
		writer.PropertyName("otherActions");
		if (otherActions != null)
		{
			writer.ArrayBegin(otherActions.Length);
			for (int i = 0; i < otherActions.Length; i++)
			{
				writer.Write(otherActions[i]);
			}
			writer.ArrayEnd();
		}
		else
		{
			writer.WriteEmptyArray();
		}
		writer.PropertyName("details");
		writer.Write(details);
		writer.PropertyName("copyButton");
		writer.Write(copyButton);
		writer.TypeEnd();
	}
```


