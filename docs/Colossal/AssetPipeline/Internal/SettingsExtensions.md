# Colossal.AssetPipeline.Internal.SettingsExtensions

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Internal`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Fields

- `private static readonly Colossal.Logging.ILog log`  
- `private static readonly System.String kTextureSubstitutionString`  
- `private static readonly System.String kModelSubstitutionString`  
- `private static readonly System.String kNormalMapSubstitutionString`  
- `private static readonly System.String kGlassSubstitutionString`  
- `private static readonly System.String kBakeEmissiveSubstitutionString`  
- `private static readonly System.String kInteriorSubstitutionString`  
- `private static readonly System.String kBaseColorMapSubstitutionString`  
- `private static readonly System.String kWorldspaceBaseColorMapSubstitutionString`  
- `private static readonly System.String kWorldspaceNormalMapSubstitutionString`  
- `private static readonly System.String kTreeSubstitutionString`  

## Methods

- `public static FormatPattern(System.String format) : System.String`  
- `public static GetMatchingValues<T>(System.Collections.Generic.List<System.ValueTuple<System.String, System.Collections.Generic.List<T>>> dictionary, System.String name, IReadOnlyCollection`1& settingNames, Colossal.AssetPipeline.Diagnostic.ReportBase report) : System.Boolean`  
- `private static ReplaceSemantic(System.String input, System.String semantic, System.String substitution) : System.String`  

