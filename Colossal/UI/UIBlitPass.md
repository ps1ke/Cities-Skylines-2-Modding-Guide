# Colossal.UI.UIBlitPass

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class public  

**Base:** `UnityEngine.Rendering.HighDefinition.CustomPass`  
**Implements:** `UnityEngine.Rendering.HighDefinition.IVersionable<UnityEngine.Rendering.HighDefinition.CustomPass+Version>`  

## Code

```csharp
public class UIBlitPass : UnityEngine.Rendering.HighDefinition.CustomPass, UnityEngine.Rendering.HighDefinition.IVersionable<UnityEngine.Rendering.HighDefinition.CustomPass+Version>
{
    private UnityEngine.Rendering.RTHandle m_UserBackground;
    private UnityEngine.Material m_BlitMaterial;

    public UIBlitPass();

    protected virtual System.Void Cleanup();
    protected virtual System.Void Execute(UnityEngine.Rendering.HighDefinition.CustomPassContext ctx);
    public System.Boolean RecreateTargetIfNeeded(Colossal.UI.UIView uiView);
    protected virtual System.Void Setup(UnityEngine.Rendering.ScriptableRenderContext renderContext, UnityEngine.Rendering.CommandBuffer cmd);
}
```


## Fields

- `private UnityEngine.Rendering.RTHandle m_UserBackground`  

```csharp
private UnityEngine.Rendering.RTHandle m_UserBackground;
```

- `private UnityEngine.Material m_BlitMaterial`  

```csharp
private UnityEngine.Material m_BlitMaterial;
```


## Constructors

- `public UIBlitPass()`  

```csharp
public UIBlitPass();
```


## Methods

- `protected virtual Cleanup() : System.Void`  

```csharp
protected virtual System.Void Cleanup();
```

- `protected virtual Execute(UnityEngine.Rendering.HighDefinition.CustomPassContext ctx) : System.Void`  

```csharp
protected virtual System.Void Execute(UnityEngine.Rendering.HighDefinition.CustomPassContext ctx);
```

- `public RecreateTargetIfNeeded(Colossal.UI.UIView uiView) : System.Boolean`  

```csharp
public System.Boolean RecreateTargetIfNeeded(Colossal.UI.UIView uiView);
```

- `protected virtual Setup(UnityEngine.Rendering.ScriptableRenderContext renderContext, UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  

```csharp
protected virtual System.Void Setup(UnityEngine.Rendering.ScriptableRenderContext renderContext, UnityEngine.Rendering.CommandBuffer cmd);
```


