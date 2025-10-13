# Colossal.Localization.LocalizationEntry

**Assembly:** `Colossal.Localization`  
**Namespace:** `Colossal.Localization`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class LocalizationEntry
{
    private readonly Colossal.Localization.LocalizationEntry+IdentifierType <type>k__BackingField;
    private readonly System.String <group>k__BackingField;
    private readonly System.String <id>k__BackingField;
    private readonly System.String <hash>k__BackingField;
    private System.Int32 m_Index;
    private System.String <value>k__BackingField;
    private System.Collections.Generic.List<System.String> <argNames>k__BackingField;
    private readonly System.String <plainIdentifier>k__BackingField;
    private readonly System.String <identifierWithoutIndex>k__BackingField;
    private System.String <fullIdentifier>k__BackingField;

    public Colossal.Localization.LocalizationEntry+IdentifierType type { get; }
    public System.String group { get; }
    public System.String id { get; }
    public System.String hash { get; }
    public System.Int32 index { get; set; }
    public System.String value { get; set; }
    public System.Collections.Generic.List<System.String> argNames { get; set; }
    public System.String plainIdentifier { get; }
    public System.String identifierWithoutIndex { get; }
    public System.String fullIdentifier { get; private set; }

    public LocalizationEntry(Colossal.Localization.LocalizationEntry+IdentifierType type, System.String group, System.String id, System.String hash, System.Int32 index, System.String value, System.Collections.Generic.List<System.String> argNames);

    private System.String GetFullIdentifier();
    private System.String GetIdentifierWithoutIndex();
    public virtual System.String ToString();
}
```


## Fields

- `private readonly Colossal.Localization.LocalizationEntry+IdentifierType <type>k__BackingField`  

```csharp
private readonly Colossal.Localization.LocalizationEntry+IdentifierType <type>k__BackingField;
```

- `private readonly System.String <group>k__BackingField`  

```csharp
private readonly System.String <group>k__BackingField;
```

- `private readonly System.String <id>k__BackingField`  

```csharp
private readonly System.String <id>k__BackingField;
```

- `private readonly System.String <hash>k__BackingField`  

```csharp
private readonly System.String <hash>k__BackingField;
```

- `private System.Int32 m_Index`  

```csharp
private System.Int32 m_Index;
```

- `private System.String <value>k__BackingField`  

```csharp
private System.String <value>k__BackingField;
```

- `private System.Collections.Generic.List<System.String> <argNames>k__BackingField`  

```csharp
private System.Collections.Generic.List<System.String> <argNames>k__BackingField;
```

- `private readonly System.String <plainIdentifier>k__BackingField`  

```csharp
private readonly System.String <plainIdentifier>k__BackingField;
```

- `private readonly System.String <identifierWithoutIndex>k__BackingField`  

```csharp
private readonly System.String <identifierWithoutIndex>k__BackingField;
```

- `private System.String <fullIdentifier>k__BackingField`  

```csharp
private System.String <fullIdentifier>k__BackingField;
```


## Properties

- `public Colossal.Localization.LocalizationEntry+IdentifierType type { get }`  

```csharp
public Colossal.Localization.LocalizationEntry+IdentifierType type { get; }
```

- `public System.String group { get }`  

```csharp
public System.String group { get; }
```

- `public System.String id { get }`  

```csharp
public System.String id { get; }
```

- `public System.String hash { get }`  

```csharp
public System.String hash { get; }
```

- `public System.Int32 index { get; set }`  

```csharp
public System.Int32 index { get; set; }
```

- `public System.String value { get; set }`  

```csharp
public System.String value { get; set; }
```

- `public System.Collections.Generic.List<System.String> argNames { get; set }`  

```csharp
public System.Collections.Generic.List<System.String> argNames { get; set; }
```

- `public System.String plainIdentifier { get }`  

```csharp
public System.String plainIdentifier { get; }
```

- `public System.String identifierWithoutIndex { get }`  

```csharp
public System.String identifierWithoutIndex { get; }
```

- `public System.String fullIdentifier { get; private set }`  

```csharp
public System.String fullIdentifier { get; private set; }
```


## Constructors

- `public LocalizationEntry(Colossal.Localization.LocalizationEntry+IdentifierType type, System.String group, System.String id, System.String hash, System.Int32 index, System.String value, System.Collections.Generic.List<System.String> argNames)`  

```csharp
public LocalizationEntry(Colossal.Localization.LocalizationEntry+IdentifierType type, System.String group, System.String id, System.String hash, System.Int32 index, System.String value, System.Collections.Generic.List<System.String> argNames);
```


## Methods

- `private GetFullIdentifier() : System.String`  

```csharp
private System.String GetFullIdentifier();
```

- `private GetIdentifierWithoutIndex() : System.String`  

```csharp
private System.String GetIdentifierWithoutIndex();
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```


## Nested types

- `Colossal.Localization.LocalizationEntry+IdentifierType`  

