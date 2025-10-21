# Game.UI.Menu.AutomaticSettings+IProxyProperty

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IProxyProperty
{
    public System.Boolean canRead { get; }
    public System.Boolean canWrite { get; }
    public System.String name { get; }
    public System.Type propertyType { get; }
    public System.Type declaringType { get; }

    public abstract T GetAttribute<T>(System.Boolean inherit);
    public abstract System.Collections.Generic.IEnumerable<T> GetAttributes<T>(System.Boolean inherit);
    public abstract System.Object GetValue(System.Object obj);
    public abstract System.Boolean HasAttribute<T>(System.Boolean inherit);
    public abstract System.Void SetValue(System.Object obj, System.Object value);
    public abstract System.Boolean TryGetAttribute<T>(T& attribute, System.Boolean inherit);
}
```


## Properties

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


## Methods

- `public abstract GetAttribute<T>(System.Boolean inherit = False) : T`  

```csharp
public abstract T GetAttribute<T>(System.Boolean inherit);
```

- `public abstract GetAttributes<T>(System.Boolean inherit = False) : System.Collections.Generic.IEnumerable<T>`  

```csharp
public abstract System.Collections.Generic.IEnumerable<T> GetAttributes<T>(System.Boolean inherit);
```

- `public abstract GetValue(System.Object obj) : System.Object`  

```csharp
public abstract System.Object GetValue(System.Object obj);
```

- `public abstract HasAttribute<T>(System.Boolean inherit = False) : System.Boolean`  

```csharp
public abstract System.Boolean HasAttribute<T>(System.Boolean inherit);
```

- `public abstract SetValue(System.Object obj, System.Object value) : System.Void`  

```csharp
public abstract System.Void SetValue(System.Object obj, System.Object value);
```

- `public abstract TryGetAttribute<T>(T& attribute, System.Boolean inherit = False) : System.Boolean`  

```csharp
public abstract System.Boolean TryGetAttribute<T>(T& attribute, System.Boolean inherit);
```


