# Colossal.UI.Fatal.ErrorPage

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI.Fatal`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private System.Collections.Generic.Dictionary<System.String, System.Action> m_ActionsMap`  
- `private System.Collections.Generic.Dictionary<UnityEngine.SystemLanguage, System.Collections.Generic.Dictionary<System.String, System.String>> m_LocalizedText`  
- `private System.String m_FontPath`  
- `private System.Exception m_Exception`  
- `private System.Boolean <isPackaged>k__BackingField`  
- `private System.String m_RootPath`  
- `private System.String <htmlText>k__BackingField`  

## Properties

- `public System.Boolean isPackaged { get; private set }`  
- `public System.String rootPath { get }`  
- `public System.String htmlText { get; private set }`  

## Constructors

- `public ErrorPage()`  

## Methods

- `public AddAction(System.String key, System.Action action) : System.Void`  
- `private static CreateReportMessage(System.String reportLocation) : System.String`  
- `private static CreateReportPackage() : System.String`  
- `public EnumerateFiles(System.String[] extensionFilters) : System.Collections.Generic.IEnumerable<Colossal.UI.Fatal.IFileStreamProvider>`  
- `public EnumerateFonts(System.String preloadPath) : System.Collections.Generic.IEnumerable<System.ValueTuple<System.String, Colossal.UI.IFontStreamProvider>>`  
- `private GetLocalizedMessage(System.Exception ex) : System.String`  
- `private static LoadTextFromCsv(System.IO.Stream stream, System.Collections.Generic.Dictionary<System.String, System.String> substitutions) : System.Void`  
- `public RebuildHtml(UnityEngine.SystemLanguage language) : System.Void`  
- `private static ReplacePlaceholders(System.String css, System.Collections.Generic.IDictionary<System.String, System.String> substitutions) : System.String`  
- `public SetFonts(System.String path, System.String packagePath) : System.Void`  
- `public SetRoot(System.String path, System.String packagePath) : System.Void`  
- `public SetStopCode(System.Exception ex) : System.Void`  
- `public TryGetAction(System.String key, System.Action& action) : System.Boolean`  

## Nested types

- `Colossal.UI.Fatal.ErrorPage+<>c__DisplayClass20_0`  
- `Colossal.UI.Fatal.ErrorPage+<>c__DisplayClass22_0`  
- `Colossal.UI.Fatal.ErrorPage+<>c__DisplayClass26_0`  
- `Colossal.UI.Fatal.ErrorPage+<EnumerateFiles>d__23`  
- `Colossal.UI.Fatal.ErrorPage+<EnumerateFonts>d__24`  

