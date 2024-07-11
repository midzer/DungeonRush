# Emscripten

## Compile

```
mkdir build
cd build
emcmake cmake ..
emmake make
```

## Link

```
emcc -O3 -flto -fno-rtti -fno-exceptions *.o -o index.html -sUSE_SDL=2 -sUSE_SDL_IMAGE=2 -sUSE_SDL_NET=2 -sUSE_SDL_MIXER=2 -sUSE_SDL_TTF=2 -sSDL2_IMAGE_FORMATS='["png"]' -sSDL2_MIXER_FORMATS='["wav","ogg"]' -sASYNCIFY -sASYNCIFY_IGNORE_INDIRECT -sASYNCIFY_ONLY=@../../../../funcs.txt -sENVIRONMENT=web --preload-file ../../../../res/@res/ --closure 1 -Wl,-u,fileno -Wl,-u,htons -Wl,-u,ntohs -sEXPORTED_RUNTIME_METHODS=['allocate']
```
