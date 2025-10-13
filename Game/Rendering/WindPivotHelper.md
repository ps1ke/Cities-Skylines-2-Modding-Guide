# Game.Rendering.WindPivotHelper

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `UnityEngine.MonoBehaviour`  

## Code

```csharp
public class WindPivotHelper : UnityEngine.MonoBehaviour
{
    public Game.Rendering.WindPivotHelper+PivotBakeMode m_BakedMode;
    public System.Boolean m_ShowBasePivot;
    public System.Boolean m_ShowLevel0Pivot;
    public System.Boolean m_ShowLevel0Guide;
    public System.Boolean m_ShowLevel1Pivot;
    public System.Boolean m_ShowLevel1Guide;
    public System.Collections.Generic.List<UnityEngine.Vector3> m_PivotsP0;
    public System.Collections.Generic.List<UnityEngine.Vector3> m_PivotsN0;
    public System.Collections.Generic.List<System.Single> m_PivotsH0;
    public System.Collections.Generic.List<UnityEngine.Vector3> m_PivotsR1;
    public System.Collections.Generic.List<UnityEngine.Vector3> m_PivotsP1;
    public System.Collections.Generic.List<UnityEngine.Vector3> m_PivotsN1;
    public System.Collections.Generic.List<System.Single> m_PivotsH1;

    public WindPivotHelper();

    public System.Void Clear();
    private System.Void OnDrawGizmosSelected();
}
```


## Fields

- `public Game.Rendering.WindPivotHelper+PivotBakeMode m_BakedMode`  

```csharp
public Game.Rendering.WindPivotHelper+PivotBakeMode m_BakedMode;
```

- `public System.Boolean m_ShowBasePivot`  

```csharp
public System.Boolean m_ShowBasePivot;
```

- `public System.Boolean m_ShowLevel0Pivot`  

```csharp
public System.Boolean m_ShowLevel0Pivot;
```

- `public System.Boolean m_ShowLevel0Guide`  

```csharp
public System.Boolean m_ShowLevel0Guide;
```

- `public System.Boolean m_ShowLevel1Pivot`  

```csharp
public System.Boolean m_ShowLevel1Pivot;
```

- `public System.Boolean m_ShowLevel1Guide`  

```csharp
public System.Boolean m_ShowLevel1Guide;
```

- `public System.Collections.Generic.List<UnityEngine.Vector3> m_PivotsP0`  

```csharp
public System.Collections.Generic.List<UnityEngine.Vector3> m_PivotsP0;
```

- `public System.Collections.Generic.List<UnityEngine.Vector3> m_PivotsN0`  

```csharp
public System.Collections.Generic.List<UnityEngine.Vector3> m_PivotsN0;
```

- `public System.Collections.Generic.List<System.Single> m_PivotsH0`  

```csharp
public System.Collections.Generic.List<System.Single> m_PivotsH0;
```

- `public System.Collections.Generic.List<UnityEngine.Vector3> m_PivotsR1`  

```csharp
public System.Collections.Generic.List<UnityEngine.Vector3> m_PivotsR1;
```

- `public System.Collections.Generic.List<UnityEngine.Vector3> m_PivotsP1`  

```csharp
public System.Collections.Generic.List<UnityEngine.Vector3> m_PivotsP1;
```

- `public System.Collections.Generic.List<UnityEngine.Vector3> m_PivotsN1`  

```csharp
public System.Collections.Generic.List<UnityEngine.Vector3> m_PivotsN1;
```

- `public System.Collections.Generic.List<System.Single> m_PivotsH1`  

```csharp
public System.Collections.Generic.List<System.Single> m_PivotsH1;
```


## Constructors

- `public WindPivotHelper()`  

```csharp
public WindPivotHelper();
```


## Methods

- `public Clear() : System.Void`  

```csharp
public void Clear()
	{
		m_PivotsP0.Clear();
		m_PivotsN0.Clear();
		m_PivotsH0.Clear();
		m_PivotsR1.Clear();
		m_PivotsP1.Clear();
		m_PivotsN1.Clear();
		m_PivotsH1.Clear();
	}
```

- `private OnDrawGizmosSelected() : System.Void`  

```csharp
private void OnDrawGizmosSelected()
	{
		Matrix4x4 localToWorldMatrix = base.transform.localToWorldMatrix;
		float num = Mathf.Max(base.transform.lossyScale.x, Mathf.Max(base.transform.lossyScale.y, base.transform.lossyScale.z));
		if (m_ShowLevel1Pivot || m_ShowLevel1Guide)
		{
			Color color = new Color(0f, 1f, 1f, 0.1f);
			for (int i = 0; i < m_PivotsP1.Count; i++)
			{
				Vector3 to = localToWorldMatrix.MultiplyPoint(m_PivotsR1[i]);
				Vector3 vector = localToWorldMatrix.MultiplyPoint(m_PivotsP1[i]);
				Vector3 vector2 = localToWorldMatrix.MultiplyVector(m_PivotsN1[i] * m_PivotsH1[i]);
				if (m_ShowLevel1Guide)
				{
					Gizmos.color = color;
					Gizmos.DrawLine(vector, to);
				}
				if (m_ShowLevel1Pivot)
				{
					Gizmos.color = Color.blue;
					Gizmos.DrawLine(vector, vector + vector2);
					Gizmos.DrawSphere(vector, 0.01f * num);
				}
			}
		}
		if (m_ShowLevel0Pivot || m_ShowLevel0Guide)
		{
			Color color2 = new Color(1f, 1f, 0f, 0.1f);
			for (int j = 0; j < m_PivotsP0.Count; j++)
			{
				Vector3 vector3 = localToWorldMatrix.MultiplyPoint(m_PivotsP0[j]);
				Vector3 vector4 = localToWorldMatrix.MultiplyVector(m_PivotsN0[j] * m_PivotsH0[j]);
				if (m_ShowLevel0Guide)
				{
					Gizmos.color = color2;
					Gizmos.DrawLine(vector3, base.transform.position);
				}
				if (m_ShowLevel0Pivot)
				{
					Gizmos.color = Color.green;
					Gizmos.DrawLine(vector3, vector3 + vector4);
					Gizmos.DrawSphere(vector3, 0.01f * num);
				}
			}
		}
		if (m_ShowBasePivot)
		{
			Gizmos.color = Color.red;
			Gizmos.DrawSphere(base.transform.position, 0.1f * num);
		}
	}
```


## Nested types

- `Game.Rendering.WindPivotHelper+PivotBakeMode`  

