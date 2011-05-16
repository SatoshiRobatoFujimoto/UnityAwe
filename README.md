UnityAwe is a simple drag-and-drop C# script for using Awesomium in Unity. Simply add WebTexture.cs, WebCoreHelper.cs, and AwesomiumMono.dll to your assets folder and drag the "WebTexture" script onto any game object or GUI texture. 

Be sure to include AwesomiumMono's dll and dependencies (everything within the build/bin/release folder in the SDK) in the assets folder and in Unity's editor folder.

To build AwesomiumMono, please check out khrona/AwesomiumSharp on GitHub.

Unity's Editor folder locations:
Windows = C:\Program Files\Unity\Editor
Mac = /Applications/Unity/Unity.app/Contents/Frameworks


Getting this working with Mac OSX can be a little complicated so I have provided full directions below:

**Build AwesomiumMono on Mac OSX:**

1. Checkout AwesomiumSharp files off of GitHub.
2. Open up MonoDevelop and create a new Solution with type "C# Library", name it "AwesomiumMono".
3. Add WebCore.cs, WebView.cs, RenderBuffer.cs, KeyboardCodes.cs, and JSValue.cs to the project.
4. Go to Project Options, and under Build -> Compiler settings, add "USING_MONO" to Define Symbols.
5. Open up WebCore.cs and change WebCore.DLLName to `"@executable_path/../Frameworks/Awesomium.framework/Versions/A/Awesomium"`
6. Build the solution (should end up with AwesomiumMono.dll in project's bin directory).

**Set Up Unity IDE:**

1. Find the "Unity" application on your hard drive.
2. Right-click, "Show Package Contents"
3. Copy Awesomium.framework (from the SDK) into "Unity/Contents/Frameworks/"

**Set Up Unity Project:**

1. Create a new Unity project/scene.
2. Check out UnityAwe from GitHub.
2. Add WebTexture.cs, WebCoreHelper.cs, and AwesomiuMono.dll to assets folder.
3. Create a new GUITexture game object in your scene.
4. Drag the WebTexture script onto your new GUITexture.
5. Modify the script properties in the Unity editor (change width, initial URL, etc.)
6. Run your scene, you should be able to render and interact with a WebView wherever you placed your GUITexture.