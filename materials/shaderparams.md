# material flags missing documentation (todo check source 2007 leaks)

## $flat
Makes the material flat shaded instead of gouraud shaded like everything else in source (i think)

from csgo materialsystem/shadersystem.cpp
```cpp
// If we're rendering flat, turn on flat mode...
if (materialVarFlags & MATERIAL_VAR_FLAT)
{
g_pShaderAPI->ShadeMode( SHADER_FLAT );
}
```

## $znearer
something to do with the zbuffer?

from csgo materialsystem/shaderlib/BaseShader.cpp
```cpp
if (flags & MATERIAL_VAR_ZNEARER)
{
s_pShaderShadow->DepthFunc( SHADER_DEPTHFUNC_NEARER );
}
```

## $envmapcameraspace
```glsl
		if( $envmapcameraspace )
		{
			&AllocateRegister( \$reflectionVector );
			&ComputeReflectionVector( $worldPos, $worldNormal, $reflectionVector );

			; transform reflection vector into view space
			dp3 oT1.x, $reflectionVector, $cViewModel0
			dp3 oT1.y, $reflectionVector, $cViewModel1
			dp3 oT1.z, $reflectionVector, $cViewModel2

			&FreeRegister( \$reflectionVector );
		}
		elsif( $envmapsphere )
		{
			&AllocateRegister( \$reflectionVector );
			&ComputeReflectionVector( $worldPos, $worldNormal, $reflectionVector );
			&ComputeSphereMapTexCoords( $reflectionVector, "oT1" );

			&FreeRegister( \$reflectionVector );
		}
		else
		{
			&ComputeReflectionVector( $worldPos, $worldNormal, "oT1" );
		}
```
no idea what would be the difference, todo check in game

"elsif" isnt valid syntax in glsl, but no idea if that matters with valve and their *perl* based workflow

removed as of csgo

noalphamod also gone as of csgo

## $envmapsphere broken: lead?
loadcubemap/loadtexture

ENVMAP - pre dx9

info.m_nEnvmap - dx9

internal directx nonsense? or engine stuff

## $envmapmode
what does it do? it's between god and gaben now

## $wireframe
forces the material to be wireframe

does it work like the wireframe shader? (no textures) or does it allow drawing fancy stuff

from csgo materialsystem/shaderlib/BaseShader.cpp
```cpp
if (flags & MATERIAL_VAR_WIREFRAME)
{
s_pShaderShadow->PolyMode( SHADER_POLYMODEFACE_FRONT_AND_BACK, SHADER_POLYMODE_LINE );
}
```

## $pearlescent
float used for holographic stuff in csgo

maybe theres some kind of mask material that exists to only enble holo on certain areas of a model but can't find docs or source code
??????

MATERIAL_VAR_AOPREPASS???
