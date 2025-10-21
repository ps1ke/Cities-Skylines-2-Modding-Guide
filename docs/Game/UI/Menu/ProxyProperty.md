# Game.UI.Menu.AutomaticSettings+ProxyProperty

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Menu.AutomaticSettings+IProxyProperty`  

## Code

```csharp
public class ProxyProperty : Game.UI.Menu.AutomaticSettings+IProxyProperty
{
    private readonly System.Reflection.PropertyInfo <property>k__BackingField;

    public System.Reflection.PropertyInfo property { get; }
    public System.Boolean canRead { get; }
    public System.Boolean canWrite { get; }
    public System.String name { get; }
    public System.Type propertyType { get; }
    public System.Type declaringType { get; }

    public ProxyProperty(System.Reflection.PropertyInfo property);

    public T GetAttribute<T>(System.Boolean inherit);
    public System.Collections.Generic.IEnumerable<T> GetAttributes<T>(System.Boolean inherit);
    public System.Object GetValue(System.Object obj);
    public System.Boolean HasAttribute<T>(System.Boolean inherit);
    public System.Void SetValue(System.Object obj, System.Object value);
    public System.Boolean TryGetAttribute<T>(T& attribute, System.Boolean inherit);
}
```


## Fields

- `private readonly System.Reflection.PropertyInfo <property>k__BackingField`  

```csharp
private readonly System.Reflection.PropertyInfo <property>k__BackingField;
```


## Properties

- `public System.Reflection.PropertyInfo property { get }`  

```csharp
public System.Reflection.PropertyInfo property { get; }
```

- `public System.Boolean canRead { get }`  

```csharp
public System.Boolean canRead { get; }
```

- `public System.Boolean canWrite { get }`  

```csharp
public System.Boolean canWrite { get; }
```

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```

- `public System.Type propertyType { get }`  

```csharp
public System.Type propertyType { get; }
```

- `public System.Type declaringType { get }`  

```csharp
public System.Type declaringType { get; }
```


## Constructors

- `public ProxyProperty(System.Reflection.PropertyInfo property)`  

```csharp
public ProxyProperty(System.Reflection.PropertyInfo property);
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


