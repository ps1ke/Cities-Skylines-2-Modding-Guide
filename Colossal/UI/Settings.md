# Colossal.UI.UIView+Settings

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public sealed struct Settings : System.IDisposable
{
    public System.UInt32 width;
    public System.UInt32 height;
    public System.Boolean acceptsInput;
    public System.Boolean enableComplexTextLayout;
    public System.Boolean enableComplexCSSSelectorsStyling;
    public System.Boolean isTransparent;
    public System.Boolean pixelPerfect;
    public System.Boolean liveReload;
    public System.String liveReloadUrl;
    public System.Int32 devServerPort;
    public System.Boolean wideTextures;
    public System.Boolean enableBackdropFilter;
    private Colossal.UI.ViewListener m_Listener;
    private Colossal.UI.TextInputHandler m_TextInputHandler;

    public static Colossal.UI.UIView+Settings New { get; }
    public Colossal.UI.ViewListener listener { get; set; }
    public Colossal.UI.TextInputHandler textInputHandler { get; set; }

    public System.Void Dispose();
    public cohtml.Net.ViewSettings ToNativeSettings();
}
```


## Fields

- `public System.UInt32 width`  

```csharp
public System.UInt32 width;
```

- `public System.UInt32 height`  

```csharp
public System.UInt32 height;
```

- `public System.Boolean acceptsInput`  

```csharp
public System.Boolean acceptsInput;
```

- `public System.Boolean enableComplexTextLayout`  

```csharp
public System.Boolean enableComplexTextLayout;
```

- `public System.Boolean enableComplexCSSSelectorsStyling`  

```csharp
public System.Boolean enableComplexCSSSelectorsStyling;
```

- `public System.Boolean isTransparent`  

```csharp
public System.Boolean isTransparent;
```

- `public System.Boolean pixelPerfect`  

```csharp
public System.Boolean pixelPerfect;
```

- `public System.Boolean liveReload`  

```csharp
public System.Boolean liveReload;
```

- `public System.String liveReloadUrl`  

```csharp
public System.String liveReloadUrl;
```

- `public System.Int32 devServerPort`  

```csharp
public System.Int32 devServerPort;
```

- `public System.Boolean wideTextures`  

```csharp
public System.Boolean wideTextures;
```

- `public System.Boolean enableBackdropFilter`  

```csharp
public System.Boolean enableBackdropFilter;
```

- `private Colossal.UI.ViewListener m_Listener`  

```csharp
private Colossal.UI.ViewListener m_Listener;
```

- `private Colossal.UI.TextInputHandler m_TextInputHandler`  

```csharp
private Colossal.UI.TextInputHandler m_TextInputHandler;
```


## Properties

- `public static Colossal.UI.UIView+Settings New { get }`  

```csharp
public static Colossal.UI.UIView+Settings New { get; }
```

- `public Colossal.UI.ViewListener listener { get; set }`  

```csharp
public Colossal.UI.ViewListener listener { get; set; }
```

- `public Colossal.UI.TextInputHandler textInputHandler { get; set }`  

```csharp
public Colossal.UI.TextInputHandler textInputHandler { get; set; }
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public ToNativeSettings() : cohtml.Net.ViewSettings`  

```csharp
public cohtml.Net.ViewSettings ToNativeSettings();
```


