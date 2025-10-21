# Game.UI.Menu.AutomaticSettings+ManualProperty

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Menu.AutomaticSettings+IProxyProperty`  

## Code

```csharp
public class ManualProperty : Game.UI.Menu.AutomaticSettings+IProxyProperty
{
    private System.Boolean <canRead>k__BackingField;
    private System.Boolean <canWrite>k__BackingField;
    private System.String <name>k__BackingField;
    private System.Type <propertyType>k__BackingField;
    private System.Type <declaringType>k__BackingField;
    private System.Action<System.Object, System.Object> <setter>k__BackingField;
    private System.Func<System.Object, System.Object> <getter>k__BackingField;
    private readonly System.Collections.Generic.List<System.Attribute> <attributes>k__BackingField;

    public System.Boolean canRead { get; set; }
    public System.Boolean canWrite { get; set; }
    public System.String name { get; set; }
    public System.Type propertyType { get; set; }
    public System.Type declaringType { get; set; }
    public System.Action<System.Object, System.Object> setter { get; set; }
    public System.Func<System.Object, System.Object> getter { get; set; }
    public System.Collections.Generic.List<System.Attribute> attributes { get; }

    public ManualProperty(System.Type declaringType, System.Type propertyType, System.String name);

    public T GetAttribute<T>(System.Boolean inherit);
    public System.Collections.Generic.IEnumerable<T> GetAttributes<T>(System.Boolean inherit);
    public System.Object GetValue(System.Object obj);
    public System.Boolean HasAttribute<T>(System.Boolean inherit);
    public System.Void SetValue(System.Object obj, System.Object value);
    public System.Boolean TryGetAttribute<T>(T& attribute, System.Boolean inherit);
}
```


## Fields

- `private System.Boolean <canRead>k__BackingField`  

```csharp
private System.Boolean <canRead>k__BackingField;
```

- `private System.Boolean <canWrite>k__BackingField`  

```csharp
private System.Boolean <canWrite>k__BackingField;
```

- `private System.String <name>k__BackingField`  

```csharp
private System.String <name>k__BackingField;
```

- `private System.Type <propertyType>k__BackingField`  

```csharp
private System.Type <propertyType>k__BackingField;
```

- `private System.Type <declaringType>k__BackingField`  

```csharp
private System.Type <declaringType>k__BackingField;
```

- `private System.Action<System.Object, System.Object> <setter>k__BackingField`  

```csharp
private System.Action<System.Object, System.Object> <setter>k__BackingField;
```

- `private System.Func<System.Object, System.Object> <getter>k__BackingField`  

```csharp
private System.Func<System.Object, System.Object> <getter>k__BackingField;
```

- `private readonly System.Collections.Generic.List<System.Attribute> <attributes>k__BackingField`  

```csharp
private readonly System.Collections.Generic.List<System.Attribute> <attributes>k__BackingField;
```


## Properties

- `public System.Boolean canRead { get; set }`  

```csharp
public System.Boolean canRead { get; set; }
```

- `public System.Boolean canWrite { get; set }`  

```csharp
public System.Boolean canWrite { get; set; }
```

- `public System.String name { get; set }`  

```csharp
public System.String name { get; set; }
```

- `public System.Type propertyType { get; set }`  

```csharp
public System.Type propertyType { get; set; }
```

- `public System.Type declaringType { get; set }`  

```csharp
public System.Type declaringType { get; set; }
```

- `public System.Action<System.Object, System.Object> setter { get; set }`  

```csharp
public System.Action<System.Object, System.Object> setter { get; set; }
```

- `public System.Func<System.Object, System.Object> getter { get; set }`  

```csharp
public System.Func<System.Object, System.Object> getter { get; set; }
```

- `public System.Collections.Generic.List<System.Attribute> attributes { get }`  

```csharp
public System.Collections.Generic.List<System.Attribute> attributes { get; }
```


## Constructors

- `public ManualProperty(System.Type declaringType, System.Type propertyType, System.String name)`  

```csharp
public ManualProperty(System.Type declaringType, System.Type propertyType, System.String name);
```


## Methods

- `public GetAttribute<T>(System.Boolean inherit = False) : T`  

```csharp
public T GetAttribute<T>(System.Boolean inherit);
```

- `public GetAttributes<T>(System.Boolean inherit = False) : System.Collections.Generic.IEnumerable<T>`  

```csharp
public System.Collections.Generic.IEnumerable<T> GetAttributes<T>(System.Boolean inherit);
```

- `public GetValue(System.Object obj) : System.Object`  

```csharp
public System.Object GetValue(System.Object obj);
```

- `public HasAttribute<T>(System.Boolean inherit = False) : System.Boolean`  

```csharp
public System.Boolean HasAttribute<T>(System.Boolean inherit);
```

- `public SetValue(System.Object obj, System.Object value) : System.Void`  

```csharp
public System.Void SetValue(System.Object obj, System.Object value);
```

- `public TryGetAttribute<T>(T& attribute, System.Boolean inherit = False) : System.Boolean`  

```csharp
public System.Boolean TryGetAttribute<T>(T& attribute, System.Boolean inherit);
```


