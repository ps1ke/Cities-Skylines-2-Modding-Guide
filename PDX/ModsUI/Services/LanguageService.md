# PDX.ModsUI.Services.LanguageService

**Assembly:** `PDX.ModsUI`  
**Namespace:** `PDX.ModsUI.Services`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `PDX.ModsUI.Services.ILanguageService`  

## Code

```csharp
public class LanguageService : PDX.ModsUI.Services.ILanguageService
{
    private readonly PDX.ModsUI.Services.ILogService _logger;
    private System.String _current;
    private static readonly System.Collections.Generic.List<System.String> <LanguagesSupported>k__BackingField;

    public System.String Default { get; }
    public System.String Current { get; set; }
    public static System.Collections.Generic.List<System.String> LanguagesSupported { get; }

    public LanguageService(System.String language, PDX.ModsUI.Services.ILogService logger);

}
```


## Fields

- `private readonly PDX.ModsUI.Services.ILogService _logger`  

```csharp
private readonly PDX.ModsUI.Services.ILogService _logger;
```

- `private System.String _current`  

```csharp
private System.String _current;
```

- `private static readonly System.Collections.Generic.List<System.String> <LanguagesSupported>k__BackingField`  

```csharp
private static readonly System.Collections.Generic.List<System.String> <LanguagesSupported>k__BackingField;
```


## Properties

- `public System.String Default { get }`  

```csharp
public System.String Default { get; }
```

- `public System.String Current { get; set }`  

```csharp
public System.String Current { get; set; }
```

- `public static System.Collections.Generic.List<System.String> LanguagesSupported { get }`  

```csharp
public static System.Collections.Generic.List<System.String> LanguagesSupported { get; }
```


## Constructors

- `public LanguageService(System.String language, PDX.ModsUI.Services.ILogService logger)`  

```csharp
public LanguageService(System.String language, PDX.ModsUI.Services.ILogService logger);
```


