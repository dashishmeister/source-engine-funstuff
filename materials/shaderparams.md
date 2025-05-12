# material flags missing documentation

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

# $envmapcameraspace
obsolete, removed from csgo

noalphamod also gone as of csgo
