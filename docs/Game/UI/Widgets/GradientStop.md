# Game.UI.Widgets.GradientStop

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public sealed struct GradientStop : Colossal.UI.Binding.IJsonWritable
{
    public System.Single offset;
    public UnityEngine.Color32 color;

    public GradientStop(System.Single offset, UnityEngine.Color32 color);

    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `public System.Single offset`  

```csharp
public System.Single offset;
```

- `public UnityEngine.Color32 color`  

```csharp
public UnityEngine.Color32 color;
```


## Constructors

- `public GradientStop(System.Single offset, UnityEngine.Color32 color)`  

```csharp
public GradientStop(System.Single offset, UnityEngine.Color32 color);
```


## Methods

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


