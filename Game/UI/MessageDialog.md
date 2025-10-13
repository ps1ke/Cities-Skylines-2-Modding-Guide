# Game.UI.MessageDialog

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class public  

**Base:** `Game.UI.ConfirmationDialogBase`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public class MessageDialog : Game.UI.ConfirmationDialogBase, Colossal.UI.Binding.IJsonWritable
{
    public MessageDialog(System.Nullable<Game.UI.Localization.LocalizedString> title, Game.UI.Localization.LocalizedString message, Game.UI.Localization.LocalizedString confirmAction, Game.UI.Localization.LocalizedString[] otherActions);
    public MessageDialog(System.Nullable<Game.UI.Localization.LocalizedString> title, Game.UI.Localization.LocalizedString message, System.Nullable<Game.UI.Localization.LocalizedString> details, System.Boolean copyButton, Game.UI.Localization.LocalizedString confirmAction, Game.UI.Localization.LocalizedString[] otherActions);

}
```


## Constructors

- `public MessageDialog(System.Nullable<Game.UI.Localization.LocalizedString> title, Game.UI.Localization.LocalizedString message, Game.UI.Localization.LocalizedString confirmAction, Game.UI.Localization.LocalizedString[] otherActions)`  

```csharp
public MessageDialog(System.Nullable<Game.UI.Localization.LocalizedString> title, Game.UI.Localization.LocalizedString message, Game.UI.Localization.LocalizedString confirmAction, Game.UI.Localization.LocalizedString[] otherActions);
```

- `public MessageDialog(System.Nullable<Game.UI.Localization.LocalizedString> title, Game.UI.Localization.LocalizedString message, System.Nullable<Game.UI.Localization.LocalizedString> details, System.Boolean copyButton, Game.UI.Localization.LocalizedString confirmAction, Game.UI.Localization.LocalizedString[] otherActions)`  

```csharp
public MessageDialog(System.Nullable<Game.UI.Localization.LocalizedString> title, Game.UI.Localization.LocalizedString message, System.Nullable<Game.UI.Localization.LocalizedString> details, System.Boolean copyButton, Game.UI.Localization.LocalizedString confirmAction, Game.UI.Localization.LocalizedString[] otherActions);
```


