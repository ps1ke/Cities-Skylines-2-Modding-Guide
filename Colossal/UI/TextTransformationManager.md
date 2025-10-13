# Colossal.UI.TextTransformationManager

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class public  

**Base:** `cohtml.Net.ITextTransformationManager`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class TextTransformationManager : cohtml.Net.ITextTransformationManager, System.IDisposable
{
    public TextTransformationManager();

    public virtual System.Boolean CaseMapCharacters(cohtml.Net.ITextTransformationManager+CaseOperation operation, System.String utf8Text, System.UInt32 bytesCount, cohtml.Net.ITextTransformationManager+TransformationResult transformed);
}
```


## Constructors

- `public TextTransformationManager()`  

```csharp
public TextTransformationManager();
```


## Methods

- `public virtual CaseMapCharacters(cohtml.Net.ITextTransformationManager+CaseOperation operation, System.String utf8Text, System.UInt32 bytesCount, cohtml.Net.ITextTransformationManager+TransformationResult transformed) : System.Boolean`  

```csharp
public virtual System.Boolean CaseMapCharacters(cohtml.Net.ITextTransformationManager+CaseOperation operation, System.String utf8Text, System.UInt32 bytesCount, cohtml.Net.ITextTransformationManager+TransformationResult transformed);
```


