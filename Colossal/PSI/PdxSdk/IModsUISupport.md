# Colossal.PSI.PdxSdk.IModsUISupport

**Assembly:** `Colossal.PSI.PdxSdk`  
**Namespace:** `Colossal.PSI.PdxSdk`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IModsUISupport
{
    public System.Boolean isModsUIActive { get; }

    public abstract System.Void ChangeLanguage(System.String locale);
    public abstract System.Void CreateModsUI();
    public abstract System.Void DestroyModsUI();
    public abstract System.Void SetPdxModsUI(Colossal.PSI.PdxSdk.IPdxModsUI pdxModsUI);
    public abstract System.Void ShowModDetail(System.Int32 id);
    public abstract System.Void ShowModsUI();
    public abstract System.Void UpdateInputMode();
}
```


## Properties

- `public System.Boolean isModsUIActive { get }`  

```csharp
public System.Boolean isModsUIActive { get; }
```


## Methods

- `public abstract ChangeLanguage(System.String locale) : System.Void`  

```csharp
public abstract System.Void ChangeLanguage(System.String locale);
```

- `public abstract CreateModsUI() : System.Void`  

```csharp
public abstract System.Void CreateModsUI();
```

- `public abstract DestroyModsUI() : System.Void`  

```csharp
public abstract System.Void DestroyModsUI();
```

- `public abstract SetPdxModsUI(Colossal.PSI.PdxSdk.IPdxModsUI pdxModsUI) : System.Void`  

```csharp
public abstract System.Void SetPdxModsUI(Colossal.PSI.PdxSdk.IPdxModsUI pdxModsUI);
```

- `public abstract ShowModDetail(System.Int32 id) : System.Void`  

```csharp
public abstract System.Void ShowModDetail(System.Int32 id);
```

- `public abstract ShowModsUI() : System.Void`  

```csharp
public abstract System.Void ShowModsUI();
```

- `public abstract UpdateInputMode() : System.Void`  

```csharp
public abstract System.Void UpdateInputMode();
```


