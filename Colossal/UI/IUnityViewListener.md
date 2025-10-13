# Colossal.UI.IUnityViewListener

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IUnityViewListener
{
    // (no members)
}
```


## Events

- `ReadyForBindings` : `System.Action`  

```csharp
public event System.Action ReadyForBindings;
```

- `BindingsReleased` : `System.Action`  

```csharp
public event System.Action BindingsReleased;
```

- `DOMBuilt` : `System.Action`  

```csharp
public event System.Action DOMBuilt;
```

- `FinishLoad` : `System.Action<System.String>`  

```csharp
public event System.Action<System.String> FinishLoad;
```

- `LoadFailed` : `System.Action<System.String, System.String>`  

```csharp
public event System.Action<System.String, System.String> LoadFailed;
```

- `NavigateTo` : `System.Func<System.String, System.Boolean>`  

```csharp
public event System.Func<System.String, System.Boolean> NavigateTo;
```


