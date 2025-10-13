# Colossal.UI.TextInputHandler

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class public  

**Base:** `cohtml.Net.ITextInputHandler`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class TextInputHandler : cohtml.Net.ITextInputHandler, System.IDisposable
{
    private cohtml.Net.IInputProxy <proxy>k__BackingField;

    protected cohtml.Net.IInputProxy proxy { protected get; private set; }

    public TextInputHandler();

    public virtual System.Void OnBlur(cohtml.Net.IInputProxy proxy);
    protected virtual System.Void OnBlurCallback();
    public virtual System.Void OnFocus(cohtml.Net.IInputProxy proxy);
    protected virtual System.Void OnFocusCallback(System.String str);
    public System.Void RefreshText(System.String text);
}
```


## Fields

- `private cohtml.Net.IInputProxy <proxy>k__BackingField`  

```csharp
private cohtml.Net.IInputProxy <proxy>k__BackingField;
```


## Properties

- `protected cohtml.Net.IInputProxy proxy { protected get; private set }`  

```csharp
protected cohtml.Net.IInputProxy proxy { protected get; private set; }
```


## Constructors

- `public TextInputHandler()`  

```csharp
public TextInputHandler();
```


## Methods

- `public virtual OnBlur(cohtml.Net.IInputProxy proxy) : System.Void`  

```csharp
public virtual System.Void OnBlur(cohtml.Net.IInputProxy proxy);
```

- `protected virtual OnBlurCallback() : System.Void`  

```csharp
protected virtual System.Void OnBlurCallback();
```

- `public virtual OnFocus(cohtml.Net.IInputProxy proxy) : System.Void`  

```csharp
public virtual System.Void OnFocus(cohtml.Net.IInputProxy proxy);
```

- `protected virtual OnFocusCallback(System.String str) : System.Void`  

```csharp
protected virtual System.Void OnFocusCallback(System.String str);
```

- `public RefreshText(System.String text) : System.Void`  

```csharp
public System.Void RefreshText(System.String text);
```


