# Game.Rendering.ZoneMeshHelpers

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class ZoneMeshHelpers
{
    public static UnityEngine.Mesh CreateMesh(Unity.Mathematics.int2 resolution, Unity.Mathematics.int2 factor);
    public static Colossal.Mathematics.Bounds3 GetBounds(Unity.Mathematics.int2 resolution);
    public static System.Int32 GetIndexCount(Unity.Mathematics.int2 resolution);
}
```


## Methods

- `public static CreateMesh(Unity.Mathematics.int2 resolution, Unity.Mathematics.int2 factor) : UnityEngine.Mesh`  

```csharp
public static Mesh CreateMesh(int2 resolution, int2 factor)
	{
		int num = (resolution.x + 1) * (resolution.y + 1) + resolution.x * resolution.y;
		int indexCount = GetIndexCount(resolution);
		Vector3[] array = new Vector3[num];
		Vector2[] array2 = new Vector2[num];
		int[] array3 = new int[indexCount];
		int num2 = 0;
		int num3 = 0;
		for (int i = 0; i <= resolution.y; i++)
		{
			float z = ((float)i - (float)resolution.y * 0.5f) * (float)factor.y * 8f;
			float y = (resolution.y - i) * factor.y;
			for (int j = 0; j <= resolution.x; j++)
			{
				float x = ((float)j - (float)resolution.x * 0.5f) * (float)factor.x * 8f;
				float x2 = (resolution.x - j) * factor.x;
				array[num2] = new Vector3(x, 0f, z);
				array2[num2] = new Vector2(x2, y);
				num2++;
			}
		}
		for (int k = 0; k < resolution.y; k++)
		{
			float z2 = ((float)k + (0.5f - (float)resolution.y * 0.5f)) * (float)factor.y * 8f;
			float y2 = ((float)resolution.y - 0.5f - (float)k) * (float)factor.y;
			for (int l = 0; l < resolution.x; l++)
			{
				float x3 = ((float)l + (0.5f - (float)resolution.x * 0.5f)) * (float)factor.x * 8f;
				float x4 = ((float)resolution.x - 0.5f - (float)l) * (float)factor.x;
				int num4 = k * (resolution.x + 1) + l;
				int num5 = num4 + 1;
				int num6 = num4 + (resolution.x + 1);
				int num7 = num4 + (resolution.x + 2);
				array3[num3++] = num2;
				array3[num3++] = num5;
				array3[num3++] = num4;
				array3[num3++] = num2;
				array3[num3++] = num7;
				array3[num3++] = num5;
				array3[num3++] = num2;
				array3[num3++] = num6;
				array3[num3++] = num7;
				array3[num3++] = num2;
				array3[num3++] = num4;
				array3[num3++] = num6;
				array[num2] = new Vector3(x3, 0f, z2);
				array2[num2] = new Vector2(x4, y2);
				num2++;
			}
		}
		return new Mesh
		{
			name = $"Zone {resolution.x}x{resolution.y}",
			vertices = array,
			uv = array2,
			triangles = array3
		};
	}
```

- `public static GetBounds(Unity.Mathematics.int2 resolution) : Colossal.Mathematics.Bounds3`  

```csharp
public static Bounds3 GetBounds(int2 resolution)
	{
		float3 @float = new float3((float)resolution.x * 4f, 0f, (float)resolution.y * 4f);
		@float.y = math.cmax(@float.xz);
		return new Bounds3(-@float, @float);
	}
```

- `public static GetIndexCount(Unity.Mathematics.int2 resolution) : System.Int32`  

```csharp
public static int GetIndexCount(int2 resolution)
	{
		return resolution.x * resolution.y * 4 * 3;
	}
```


