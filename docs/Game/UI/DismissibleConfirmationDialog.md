# Game.UI.DismissibleConfirmationDialog

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class public  

**Base:** `Game.UI.ConfirmationDialogBase`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public class DismissibleConfirmationDialog : Game.UI.ConfirmationDialogBase, Colossal.UI.Binding.IJsonWritable
{
    protected System.Boolean dismissible { protected get; }

    public DismissibleConfirmationDialog(System.Nullable<Game.UI.Localization.LocalizedString> title, Game.UI.Localization.LocalizedString message, Game.UI.Localization.LocalizedString confirmAction, System.Nullable<Game.UI.Localization.LocalizedString> cancelAction, Game.UI.Localization.LocalizedString[] otherActions);

}
```


## Properties

- `protected System.Boolean dismissible { protected get }`  

```csharp
protected System.Boolean dismissible { protected get; }
```


## Constructors

- `public DismissibleConfirmationDialog(System.Nullable<Game.UI.Localization.LocalizedString> title, Game.UI.Localization.LocalizedString message, Game.UI.Localization.LocalizedString confirmAction, System.Nullable<Game.UI.Localization.LocalizedString> cancelAction, Game.UI.Localization.LocalizedString[] otherActions)`  

```csharp
public DismissibleConfirmationDialog(System.Nullable<Game.UI.Localization.LocalizedString> title, Game.UI.Localization.LocalizedString message, Game.UI.Localization.LocalizedString confirmAction, System.Nullable<Game.UI.Localization.LocalizedString> cancelAction, Game.UI.Localization.LocalizedString[] otherActions);
```


