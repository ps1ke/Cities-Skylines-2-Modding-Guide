# Colossal.AssetPipeline.Diagnostic.Report+Prefab

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Diagnostic`  

**Type:** class public  

**Base:** `Colossal.AssetPipeline.Diagnostic.ReportBase`  

## Code

```csharp
public class Prefab : Colossal.AssetPipeline.Diagnostic.ReportBase
{
    public readonly System.String name;
    private readonly System.Collections.Generic.List<Colossal.AssetPipeline.Diagnostic.Report+Prefab+Component> m_Components;

    public System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.Diagnostic.Report+Prefab+Component> components { get; }
    public System.Int32 errorsCount { get; }
    public System.Boolean hasErrors { get; }
    public System.Int32 warningsCount { get; }
    public System.Boolean hasWarnings { get; }

    public Prefab(System.String name);

    public Colossal.AssetPipeline.Diagnostic.Report+Prefab+Component AddComponent(System.String name);
    public virtual System.String ToString();
}
```


## Fields

- `public readonly System.String name`  

```csharp
public readonly System.String name;
```

- `private readonly System.Collections.Generic.List<Colossal.AssetPipeline.Diagnostic.Report+Prefab+Component> m_Components`  

```csharp
private readonly System.Collections.Generic.List<Colossal.AssetPipeline.Diagnostic.Report+Prefab+Component> m_Components;
```


## Properties

- `public System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.Diagnostic.Report+Prefab+Component> components { get }`  

```csharp
public System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.Diagnostic.Report+Prefab+Component> components { get; }
```

- `public System.Int32 errorsCount { get }`  

```csharp
public System.Int32 errorsCount { get; }
```

- `public System.Boolean hasErrors { get }`  

```csharp
public System.Boolean hasErrors { get; }
```

- `public System.Int32 warningsCount { get }`  

```csharp
public System.Int32 warningsCount { get; }
```

- `public System.Boolean hasWarnings { get }`  

```csharp
public System.Boolean hasWarnings { get; }
```


## Constructors

- `public Prefab(System.String name)`  

```csharp
public Prefab(System.String name);
```


## Methods

- `public AddComponent(System.String name) : Colossal.AssetPipeline.Diagnostic.Report+Prefab+Component`  

```csharp
public Colossal.AssetPipeline.Diagnostic.Report+Prefab+Component AddComponent(System.String name);
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```


## Nested types

- `Colossal.AssetPipeline.Diagnostic.Report+Prefab+Component`  

