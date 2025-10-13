# Colossal.AssetPipeline.Internal.SettingsExtensions

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Internal`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class SettingsExtensions
{
    private static readonly Colossal.Logging.ILog log;
    private static readonly System.String kTextureSubstitutionString;
    private static readonly System.String kModelSubstitutionString;
    private static readonly System.String kNormalMapSubstitutionString;
    private static readonly System.String kGlassSubstitutionString;
    private static readonly System.String kBakeEmissiveSubstitutionString;
    private static readonly System.String kInteriorSubstitutionString;
    private static readonly System.String kBaseColorMapSubstitutionString;
    private static readonly System.String kWorldspaceBaseColorMapSubstitutionString;
    private static readonly System.String kWorldspaceNormalMapSubstitutionString;
    private static readonly System.String kTreeSubstitutionString;

    public static System.String FormatPattern(System.String format);
    public static System.Boolean GetMatchingValues<T>(System.Collections.Generic.List<System.ValueTuple<System.String, System.Collections.Generic.List<T>>> dictionary, System.String name, IReadOnlyCollection`1& settingNames, Colossal.AssetPipeline.Diagnostic.ReportBase report);
    private static System.String ReplaceSemantic(System.String input, System.String semantic, System.String substitution);
}
```


## Fields

- `private static readonly Colossal.Logging.ILog log`  

```csharp
private static readonly Colossal.Logging.ILog log;
```

- `private static readonly System.String kTextureSubstitutionString`  

```csharp
private static readonly System.String kTextureSubstitutionString;
```

- `private static readonly System.String kModelSubstitutionString`  

```csharp
private static readonly System.String kModelSubstitutionString;
```

- `private static readonly System.String kNormalMapSubstitutionString`  

```csharp
private static readonly System.String kNormalMapSubstitutionString;
```

- `private static readonly System.String kGlassSubstitutionString`  

```csharp
private static readonly System.String kGlassSubstitutionString;
```

- `private static readonly System.String kBakeEmissiveSubstitutionString`  

```csharp
private static readonly System.String kBakeEmissiveSubstitutionString;
```

- `private static readonly System.String kInteriorSubstitutionString`  

```csharp
private static readonly System.String kInteriorSubstitutionString;
```

- `private static readonly System.String kBaseColorMapSubstitutionString`  

```csharp
private static readonly System.String kBaseColorMapSubstitutionString;
```

- `private static readonly System.String kWorldspaceBaseColorMapSubstitutionString`  

```csharp
private static readonly System.String kWorldspaceBaseColorMapSubstitutionString;
```

- `private static readonly System.String kWorldspaceNormalMapSubstitutionString`  

```csharp
private static readonly System.String kWorldspaceNormalMapSubstitutionString;
```

- `private static readonly System.String kTreeSubstitutionString`  

```csharp
private static readonly System.String kTreeSubstitutionString;
```


## Methods

- `public static FormatPattern(System.String format) : System.String`  

```csharp
public static System.String FormatPattern(System.String format);
```

- `public static GetMatchingValues<T>(System.Collections.Generic.List<System.ValueTuple<System.String, System.Collections.Generic.List<T>>> dictionary, System.String name, IReadOnlyCollection`1& settingNames, Colossal.AssetPipeline.Diagnostic.ReportBase report) : System.Boolean`  

```csharp
public static System.Boolean GetMatchingValues<T>(System.Collections.Generic.List<System.ValueTuple<System.String, System.Collections.Generic.List<T>>> dictionary, System.String name, IReadOnlyCollection`1& settingNames, Colossal.AssetPipeline.Diagnostic.ReportBase report);
```

- `private static ReplaceSemantic(System.String input, System.String semantic, System.String substitution) : System.String`  

```csharp
private static System.String ReplaceSemantic(System.String input, System.String semantic, System.String substitution);
```


