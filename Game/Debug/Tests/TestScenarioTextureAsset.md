# Game.Debug.Tests.TestScenarioTextureAsset

**Assembly:** `Game.TestScenarios`  
**Namespace:** `Game.Debug.Tests`  

**Type:** class public  

**Base:** `Colossal.TestFramework.TestScenario`  
**Implements:** `Colossal.TestFramework.ITestStep`  

**Attributes:** `TestDescriptor`  

## Code

```csharp
public class TestScenarioTextureAsset : Colossal.TestFramework.TestScenario, Colossal.TestFramework.ITestStep
{
    private System.String m_Path;

    public TestScenarioTextureAsset();

    private UnityEngine.Texture2D CreateTex2D(System.String name, System.Int32 size);
    private UnityEngine.Texture2DArray CreateTex2DArray(System.String name);
    protected virtual System.Threading.Tasks.Task OnCleanup();
    protected virtual System.Threading.Tasks.Task OnPrepare();
    private System.Void SetNonDefaultProperties(UnityEngine.Texture tex);
    private System.Void TestMidMip();
    private System.Void TestTexture(Game.Debug.Tests.TestScenarioTextureAsset+TestTextureAsset asset);
    public System.Void TestTexture2D();
    public System.Void TestTexture2DArray();
    public System.Void TestTexture2DSaveMipBias14();
    public System.Void TestTexture2DSaveMipBias21();
    public System.Void TestTextureFrom2DArray();
    public System.Void TestTextureFrom2DArraySaveMipBias14();
    public System.Void TestTextureFrom2DArraySaveMipBias21();
}
```


## Fields

- `private System.String m_Path`  

```csharp
private System.String m_Path;
```


## Constructors

- `public TestScenarioTextureAsset()`  

```csharp
public TestScenarioTextureAsset();
```


## Methods

- `private CreateTex2D(System.String name, System.Int32 size = 512) : UnityEngine.Texture2D`  

```csharp
private UnityEngine.Texture2D CreateTex2D(System.String name, System.Int32 size);
```

- `private CreateTex2DArray(System.String name) : UnityEngine.Texture2DArray`  

```csharp
private UnityEngine.Texture2DArray CreateTex2DArray(System.String name);
```

- `protected virtual OnCleanup() : System.Threading.Tasks.Task`  

```csharp
protected virtual System.Threading.Tasks.Task OnCleanup();
```

- `protected virtual OnPrepare() : System.Threading.Tasks.Task`  

```csharp
protected virtual System.Threading.Tasks.Task OnPrepare();
```

- `private SetNonDefaultProperties(UnityEngine.Texture tex) : System.Void`  

```csharp
private System.Void SetNonDefaultProperties(UnityEngine.Texture tex);
```

- `private TestMidMip() : System.Void`  

```csharp
private System.Void TestMidMip();
```

- `private TestTexture(Game.Debug.Tests.TestScenarioTextureAsset+TestTextureAsset asset) : System.Void`  

```csharp
private System.Void TestTexture(Game.Debug.Tests.TestScenarioTextureAsset+TestTextureAsset asset);
```

- `public TestTexture2D() : System.Void`  

```csharp
public System.Void TestTexture2D();
```

- `public TestTexture2DArray() : System.Void`  

```csharp
public System.Void TestTexture2DArray();
```

- `public TestTexture2DSaveMipBias14() : System.Void`  

```csharp
public System.Void TestTexture2DSaveMipBias14();
```

- `public TestTexture2DSaveMipBias21() : System.Void`  

```csharp
public System.Void TestTexture2DSaveMipBias21();
```

- `public TestTextureFrom2DArray() : System.Void`  

```csharp
public System.Void TestTextureFrom2DArray();
```

- `public TestTextureFrom2DArraySaveMipBias14() : System.Void`  

```csharp
public System.Void TestTextureFrom2DArraySaveMipBias14();
```

- `public TestTextureFrom2DArraySaveMipBias21() : System.Void`  

```csharp
public System.Void TestTextureFrom2DArraySaveMipBias21();
```


## Nested types

- `Game.Debug.Tests.TestScenarioTextureAsset+TestTextureAsset`  

