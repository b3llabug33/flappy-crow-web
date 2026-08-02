# Flappy Crow (Web)

Unity WebGL build of [flappyCrow](https://github.com/b3llabug33/flappyCrow), so it can run on my website instead of just in the Unity Editor.

## Running it

Serve this folder with any static file server and open `index.html` — it can't be opened directly as a `file://` URL, browsers block WebAssembly from loading that way.

```bash
python -m http.server 8000
```

Built with compression disabled so it works on any plain static host (no special server headers needed for `.br`/`.gz` files).

## Rebuilding

From the main `flappyCrow` project, there's an editor script at `Assets/Editor/WebGLBuildScript.cs`. Run it headless with:

```bash
Unity.exe -batchmode -quit -nographics -projectPath "<path to flappy crow>" -executeMethod WebGLBuildScript.PerformBuild -buildTarget WebGL
```

Then copy the contents of the project's `WebGLBuild/` folder into this repo.
