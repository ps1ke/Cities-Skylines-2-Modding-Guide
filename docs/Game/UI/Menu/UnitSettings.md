# Game.UI.Menu.OptionsUISystem+UnitSettings

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`, `System.IEquatable<Game.UI.Menu.OptionsUISystem+UnitSettings>`  

## Code

```csharp
public sealed struct UnitSettings : Colossal.UI.Binding.IJsonWritable, System.IEquatable<Game.UI.Menu.OptionsUISystem+UnitSettings>
{
    public Game.Settings.InterfaceSettings+TimeFormat timeFormat;
    public Game.Settings.InterfaceSettings+TemperatureUnit temperatureUnit;
    public Game.Settings.InterfaceSettings+UnitSystem unitSystem;

    public UnitSettings(Game.Settings.InterfaceSettings settings);

    public System.Boolean Equals(Game.UI.Menu.OptionsUISystem+UnitSettings other);
    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `public Game.Settings.InterfaceSettings+TimeFormat timeFormat`  

```csharp
public Game.Settings.InterfaceSettings+TimeFormat timeFormat;
```

- `public Game.Settings.InterfaceSettings+TemperatureUnit temperatureUnit`  

```csharp
public Game.Settings.InterfaceSettings+TemperatureUnit temperatureUnit;
```

- `public Game.Settings.InterfaceSettings+UnitSystem unitSystem`  

```csharp
public Game.Settings.InterfaceSettings+UnitSystem unitSystem;
```


## Constructors

- `public UnitSettings(Game.Settings.InterfaceSettings settings)`  

```csharp
public UnitSettings(Game.Settings.InterfaceSettings settings);
```


## Methods

- `public Equals(Game.UI.Menu.OptionsUISystem+UnitSettings other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.UI.Menu.OptionsUISystem+UnitSettings other);
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


