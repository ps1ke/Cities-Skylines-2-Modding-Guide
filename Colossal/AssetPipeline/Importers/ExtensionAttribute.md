# Colossal.AssetPipeline.Importers.ExtensionAttribute

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Importers`  

**Type:** class public  

**Base:** `System.Attribute`  
**Implements:** `System.Collections.Generic.IEnumerable<System.String>`, `System.Collections.IEnumerable`  

**Attributes:** `Usage`  

## Code

```csharp
public class ExtensionAttribute : System.Attribute, System.Collections.Generic.IEnumerable<System.String>, System.Collections.IEnumerable
{
    private readonly System.String[] extensions;

    public ExtensionAttribute(System.String[] extensions);

    public System.Collections.Generic.IEnumerator<System.String> GetEnumerator();
    private System.Collections.IEnumerator System.Collections.IEnumerable.GetEnumerator();
}
```


## Fields

- `private readonly System.String[] extensions`  

```csharp
private readonly System.String[] extensions;
```


## Constructors

- `public ExtensionAttribute(System.String[] extensions)`  

```csharp
public ExtensionAttribute(System.String[] extensions);
```


## Methods

- `public GetEnumerator() : System.Collections.Generic.IEnumerator<System.String>`  

```csharp
public System.Collections.Generic.IEnumerator<System.String> GetEnumerator();
```

- `private System.Collections.IEnumerable.GetEnumerator() : System.Collections.IEnumerator`  

```csharp
private System.Collections.IEnumerator System.Collections.IEnumerable.GetEnumerator();
```


