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
what does it do? it's between god and gaben now

can't use it at the same time as envmapsphere

obsolete, removed from csgo

noalphamod also gone as of csgo

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
