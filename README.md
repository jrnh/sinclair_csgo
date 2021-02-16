# sinclair_csgo
- My CS:GO cheat, written with performance in mind. 
- Currently **in development**, and I plan to keep this as such!

# Credits
- @swoopae for his hasher.
- Other creators from whom I might've taken minimal contributions such as enumerators for various matters or even inspiration.

# Adresses (signatures)
- Addresses are stored at entry point in an array, being accessable by the StaticAddresses enumerator.
- It would not be relevant to list every stored address, as you can directly peek within the PE utilities header to see them fairly verboosely listed within an enumerator.

# Interfaces
- Interfaces are stored at entry point, and are accessible in the interfaces prototypes namespace.
- These are the current available interfaces:
  - IBaseClientDLL
  - ClientModeShared
  - CGlobalVarsBase
  - IVEngineClient
  - IClientEntityList
  - IEngineTraceClient
  - ISurface
  - ICVar
  - IInputSystem
  - CModelInfo

# Hooks
- Sinclair currently uses the GameOverlayRenderer.dll hooking utilities, and it comes with these specific hooks:
  - CreateMove (ClientModeShared one)
  - DrawCrosshair
  - FrameStageNotify
  - GetColorModulation
  - GetCSWpnData
  - GetCurrentGameType
  - IsUsingStaticPropDebugModes
  - Engine VGui Paint
  - PushNotice (CCSGOHudChat one)
  - SendNetMsg (CNetChan one)
  - 'vsnprintf' (Game formatting function)

# Props (Netvars)
- Sinclair stores every prop with it's submember's offsets in a double unordered map at entry point that uses hashes. 
- Alternatives could've been chose but it'd be likely that they'd be worse.

# Design
- Sinclair is designed with what'd perform the best in mind, explaining the templates 'abuse'. 
- This could be a trade off, due to possibly extended compilation times, but this should not be noticeable when compiling on computers that benefit from the multi-processor option.

# Features
WIP