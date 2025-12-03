# XKinect Plugin for Unreal Engine 4

A plugin for integrating Microsoft Kinect v2.0 sensor support into Unreal Engine 4 projects.

## Prerequisites

Before installing this plugin, ensure you have:

1. **Unreal Engine 4** installed
2. **Microsoft Kinect SDK v2.0** installed
   - Download from: [Microsoft Kinect for Windows SDK 2.0](https://www.microsoft.com/en-us/download/details.aspx?id=44561)
   - The SDK should be installed to: `C:\Program Files\Microsoft SDKs\Kinect\v2.0_1409\`
3. **Kinect v2.0 sensor** connected to your computer

## Installation

### Step 1: Copy the Plugin Folder

1. Navigate to your Unreal Engine 4 project directory
2. If it doesn't exist, create a `Plugins` folder in your project root directory
3. Copy the entire `XKinect` folder into the `Plugins` directory

Your project structure should look like this:

```
YourProject/
├── Content/
├── Config/
├── Plugins/
│   └── XKinect/
│       ├── Binaries/
│       ├── Resources/
│       ├── Source/
│       └── XKinect.uplugin
└── YourProject.uproject
```

### Step 2: Enable the Plugin

1. Open your Unreal Engine 4 project
2. Go to **Edit → Plugins**
3. In the Plugins window, search for "XKinect"
4. Check the box next to **XKinect** to enable it
5. Click **Restart Now** when prompted (or restart the editor manually)

### Step 3: Rebuild the Plugin (if needed)

If the plugin doesn't appear or you encounter compilation errors:

1. Right-click on your `.uproject` file
2. Select **Generate Visual Studio project files**
3. Open the generated `.sln` file in Visual Studio
4. Build the solution (Build → Build Solution)
5. Restart Unreal Engine 4

## Usage

### In C++

1. Add the XKinect module to your project's `Build.cs` file:

   ```cpp
   PublicDependencyModuleNames.AddRange(new string[] { "XKinect" });
   ```

2. Include the header:

   ```cpp
   #include "KinectActor.h"
   ```

3. Use `AKinectActor` in your code or spawn it in the world

### In Blueprints

1. In the Content Browser, right-click and select **Blueprint Class**
2. Search for "Kinect Actor" and select it as the parent class
3. You can now use the following Blueprint functions:
   - `Get Joint Position` - Get the position of a specific joint
   - `Get Joint Rotation` - Get the rotation of a specific joint
   - `Get Left Hand State` - Check if left hand is open/closed
   - `Get Right Hand State` - Check if right hand is open/closed
   - `Get Kinect Connected` - Check if Kinect is connected

## Features

- Real-time body tracking
- Joint position and rotation data
- Hand state detection (open/closed)
- Blueprint integration
- C++ API access

## Troubleshooting

- **Plugin not appearing**: Make sure the plugin is in the correct `Plugins` folder and that you've enabled it in the Plugins window
- **Compilation errors**: Ensure the Kinect SDK v2.0 is installed in the default location (`C:\Program Files\Microsoft SDKs\Kinect\v2.0_1409\`)
- **Kinect not detected**: Verify that your Kinect sensor is properly connected and the Kinect SDK runtime is installed

## Notes

- This plugin is designed for **Kinect v2.0** only
- The plugin requires Windows and the Kinect SDK v2.0 to be installed
- Make sure your project is set to use C++ (not Blueprint-only)

## License

See LICENSE file for details.

## Author

Created by Khosbilegt B.
