# Game.UI.InGame.PostVehicleSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.VehicleSection`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PostVehicleSection : Game.UI.InGame.VehicleSection, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    protected System.String group { protected get; }

    public PostVehicleSection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    private System.Boolean Visible();
}
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```


## Constructors

- `public PostVehicleSection()`  

```csharp
public PostVehicleSection();
```


## Methods

- `protected virtual OnProcess() : System.Void`  

```csharp
protected virtual System.Void OnProcess();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private Visible() : System.Boolean`  

```csharp
private System.Boolean Visible();
```


