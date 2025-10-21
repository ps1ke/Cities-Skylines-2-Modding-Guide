# Game.UI.Menu.MenuUISystem+LoadGameArgs

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonReadable`  

## Code

```csharp
public sealed struct LoadGameArgs : Colossal.UI.Binding.IJsonReadable
{
    public System.String saveId;
    public System.String cityName;
    public System.Collections.Generic.Dictionary<System.String, System.Boolean> options;
    public System.String gameMode;

    public System.Void Read(Colossal.UI.Binding.IJsonReader reader);
}
```


## Fields

- `public System.String saveId`  

```csharp
public System.String saveId;
```

- `public System.String cityName`  

```csharp
public System.String cityName;
```

- `public System.Collections.Generic.Dictionary<System.String, System.Boolean> options`  

```csharp
public System.Collections.Generic.Dictionary<System.String, System.Boolean> options;
```

- `public System.String gameMode`  

```csharp
public System.String gameMode;
```


## Methods

- `public Read(Colossal.UI.Binding.IJsonReader reader) : System.Void`  

```csharp
public System.Void Read(Colossal.UI.Binding.IJsonReader reader);
```


