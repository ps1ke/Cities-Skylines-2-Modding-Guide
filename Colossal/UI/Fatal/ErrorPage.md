# Colossal.UI.Fatal.ErrorPage

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI.Fatal`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class ErrorPage
{
    private System.Collections.Generic.Dictionary<System.String, System.Action> m_ActionsMap;
    private System.Collections.Generic.Dictionary<UnityEngine.SystemLanguage, System.Collections.Generic.Dictionary<System.String, System.String>> m_LocalizedText;
    private System.String m_FontPath;
    private System.Exception m_Exception;
    private System.Boolean <isPackaged>k__BackingField;
    private System.String m_RootPath;
    private System.String <htmlText>k__BackingField;

    public System.Boolean isPackaged { get; private set; }
    public System.String rootPath { get; }
    public System.String htmlText { get; private set; }

    public ErrorPage();

    public System.Void AddAction(System.String key, System.Action action);
    private static System.String CreateReportMessage(System.String reportLocation);
    private static System.String CreateReportPackage();
    public System.Collections.Generic.IEnumerable<Colossal.UI.Fatal.IFileStreamProvider> EnumerateFiles(System.String[] extensionFilters);
    public System.Collections.Generic.IEnumerable<System.ValueTuple<System.String, Colossal.UI.IFontStreamProvider>> EnumerateFonts(System.String preloadPath);
    private System.String GetLocalizedMessage(System.Exception ex);
    private static System.Void LoadTextFromCsv(System.IO.Stream stream, System.Collections.Generic.Dictionary<System.String, System.String> substitutions);
    public System.Void RebuildHtml(UnityEngine.SystemLanguage language);
    private static System.String ReplacePlaceholders(System.String css, System.Collections.Generic.IDictionary<System.String, System.String> substitutions);
    public System.Void SetFonts(System.String path, System.String packagePath);
    public System.Void SetRoot(System.String path, System.String packagePath);
    public System.Void SetStopCode(System.Exception ex);
    public System.Boolean TryGetAction(System.String key, System.Action& action);
}
```


## Fields

- `private System.Collections.Generic.Dictionary<System.String, System.Action> m_ActionsMap`  

```csharp
private System.Collections.Generic.Dictionary<System.String, System.Action> m_ActionsMap;
```

- `private System.Collections.Generic.Dictionary<UnityEngine.SystemLanguage, System.Collections.Generic.Dictionary<System.String, System.String>> m_LocalizedText`  

```csharp
private System.Collections.Generic.Dictionary<UnityEngine.SystemLanguage, System.Collections.Generic.Dictionary<System.String, System.String>> m_LocalizedText;
```

- `private System.String m_FontPath`  

```csharp
private System.String m_FontPath;
```

- `private System.Exception m_Exception`  

```csharp
private System.Exception m_Exception;
```

- `private System.Boolean <isPackaged>k__BackingField`  

```csharp
private System.Boolean <isPackaged>k__BackingField;
```

- `private System.String m_RootPath`  

```csharp
private System.String m_RootPath;
```

- `private System.String <htmlText>k__BackingField`  

```csharp
private System.String <htmlText>k__BackingField;
```


## Properties

- `public System.Boolean isPackaged { get; private set }`  

```csharp
public System.Boolean isPackaged { get; private set; }
```

- `public System.String rootPath { get }`  

```csharp
public System.String rootPath { get; }
```

- `public System.String htmlText { get; private set }`  

```csharp
public System.String htmlText { get; private set; }
```


## Constructors

- `public ErrorPage()`  

```csharp
public ErrorPage();
```


## Methods

- `public AddAction(System.String key, System.Action action) : System.Void`  

```csharp
public System.Void AddAction(System.String key, System.Action action);
```

- `private static CreateReportMessage(System.String reportLocation) : System.String`  

```csharp
private static System.String CreateReportMessage(System.String reportLocation);
```

- `private static CreateReportPackage() : System.String`  

```csharp
private static System.String CreateReportPackage();
```

- `public EnumerateFiles(System.String[] extensionFilters) : System.Collections.Generic.IEnumerable<Colossal.UI.Fatal.IFileStreamProvider>`  

```csharp
public System.Collections.Generic.IEnumerable<Colossal.UI.Fatal.IFileStreamProvider> EnumerateFiles(System.String[] extensionFilters);
```

- `public EnumerateFonts(System.String preloadPath) : System.Collections.Generic.IEnumerable<System.ValueTuple<System.String, Colossal.UI.IFontStreamProvider>>`  

```csharp
public System.Collections.Generic.IEnumerable<System.ValueTuple<System.String, Colossal.UI.IFontStreamProvider>> EnumerateFonts(System.String preloadPath);
```

- `private GetLocalizedMessage(System.Exception ex) : System.String`  

```csharp
private System.String GetLocalizedMessage(System.Exception ex);
```

- `private static LoadTextFromCsv(System.IO.Stream stream, System.Collections.Generic.Dictionary<System.String, System.String> substitutions) : System.Void`  

```csharp
private static System.Void LoadTextFromCsv(System.IO.Stream stream, System.Collections.Generic.Dictionary<System.String, System.String> substitutions);
```

- `public RebuildHtml(UnityEngine.SystemLanguage language) : System.Void`  

```csharp
public System.Void RebuildHtml(UnityEngine.SystemLanguage language);
```

- `private static ReplacePlaceholders(System.String css, System.Collections.Generic.IDictionary<System.String, System.String> substitutions) : System.String`  

```csharp
private static System.String ReplacePlaceholders(System.String css, System.Collections.Generic.IDictionary<System.String, System.String> substitutions);
```

- `public SetFonts(System.String path, System.String packagePath) : System.Void`  

```csharp
public System.Void SetFonts(System.String path, System.String packagePath);
```

- `public SetRoot(System.String path, System.String packagePath) : System.Void`  

```csharp
public System.Void SetRoot(System.String path, System.String packagePath);
```

- `public SetStopCode(System.Exception ex) : System.Void`  

```csharp
public System.Void SetStopCode(System.Exception ex);
```

- `public TryGetAction(System.String key, System.Action& action) : System.Boolean`  

```csharp
public System.Boolean TryGetAction(System.String key, System.Action& action);
```


## Nested types

- `Colossal.UI.Fatal.ErrorPage+<>c__DisplayClass20_0`  
- `Colossal.UI.Fatal.ErrorPage+<>c__DisplayClass22_0`  
- `Colossal.UI.Fatal.ErrorPage+<>c__DisplayClass26_0`  
- `Colossal.UI.Fatal.ErrorPage+<EnumerateFiles>d__23`  
- `Colossal.UI.Fatal.ErrorPage+<EnumerateFonts>d__24`  

