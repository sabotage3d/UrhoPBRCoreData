# UrhoPBRCoreData

PBR based shaders and some example techniques for Urho3D

### For All Workflows

The **PBR** preprocessor definition is required. Use the **IBL** preprocessor definition for image based lighting.
Use the **AO** preprocessor definition if including an ambient occlusion map

### Specular Glossines or Specular Roughness workflows

For specular glossiness

Always use the **SPECMAP** preprocessor definition to use an RGB channels of Specular texture as specular color

For glossiness, use specular texture's Alpha channel to define glossiness (0 rough, 1 smooth).

Use **ROUGHNESS** preprocessor definition to use the specular texture's Alpha channel to define roughness (0 smooth, 1 rough).

### Rough Metal or Glossy Metal workflows

Metalness is defined int he specular texture's G channel.

Use **Roughness** preprocessor defniition to use the R channel of the specular texture as roughness (0 smooth, 1 rough). Otherwise it will be treated as glossiness (0 rough, 1 smooth)

To use the R channel

---

### Standard Specular Glossiness Example

Shader preprocess defines: PBR SPECMAP IBL AO

Specular texture: RGB = color, A = glossiness

### Standard Roughness Metalness Example

Shader preprocessor defines: PBR ROUGHNESS IBL AO

Specular texture: R = roughness, G = metallness
