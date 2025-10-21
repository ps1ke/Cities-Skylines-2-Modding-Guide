# Game.UI.Menu.ParadoxBindings+LegalDocumentDialog

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `Game.UI.Menu.ParadoxBindings+ParadoxDialog`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public class LegalDocumentDialog : Game.UI.Menu.ParadoxBindings+ParadoxDialog, Colossal.UI.Binding.IJsonWritable
{
    public readonly Colossal.PSI.PdxSdk.LegalDocument document;
    public readonly System.Boolean agreementRequired;
    public readonly System.String confirmLabel;

    public LegalDocumentDialog(Colossal.PSI.PdxSdk.LegalDocument document, System.Boolean agreementRequired);

    public virtual System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `public readonly Colossal.PSI.PdxSdk.LegalDocument document`  

```csharp
public readonly Colossal.PSI.PdxSdk.LegalDocument document;
```

- `public readonly System.Boolean agreementRequired`  

```csharp
public readonly System.Boolean agreementRequired;
```

- `public readonly System.String confirmLabel`  

```csharp
public readonly System.String confirmLabel;
```


## Constructors

- `public LegalDocumentDialog(Colossal.PSI.PdxSdk.LegalDocument document, System.Boolean agreementRequired = True)`  

```csharp
public LegalDocumentDialog(Colossal.PSI.PdxSdk.LegalDocument document, System.Boolean agreementRequired);
```


## Methods

- `public virtual Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public virtual System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


