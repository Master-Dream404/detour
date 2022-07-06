# detour for my new video https://www.youtube.com/channel/UCdeJ5CSi64DimPbLJUuFEAg and pattons 48 89 5C 24 ? 57 48 83 EC ? 48 8B F9 48 8B 89 ? ? ? ? E8 ? ? ? ? 83 BF ? ? ? ? ?



```c++
BOOL APIENTRY DllMain( HMODULE hModule,
                       DWORD  ul_reason_for_call,
                       LPVOID lpReserved
                     )
{
    switch (ul_reason_for_call)
    {
    case DLL_PROCESS_ATTACH:

        DetourTransactionBegin();
        DetourUpdateThread(GetCurrentThread());
        DetourAttach(&(LPVOID&)_mhook, &Hook_m_manager);
        DetourTransactionCommit();


    case DLL_THREAD_ATTACH:
    case DLL_THREAD_DETACH:
    case DLL_PROCESS_DETACH:
        break;
    }
    return TRUE;
}
```

