# R.E.P.O. Unity Project Setup

How to develop Unity based mods for R.E.P.O.

The Unity workflow is used to create content for REPOLib without writing code. However, custom scripts can be added.
This is mainly needed for creating Enemies, Levels, Valuables and Items!

## Setup the Unity Editor

- **Unity Hub:** Download & Install [Unity Hub](https://unity.com/download).
- **Unity Editor:** Install the Unity Editor version [2022.3.62f3](unityhub://2022.3.62f3/96770f904ca7).
- **.NET SDK**: Version 6.0 or higher. This is required for AssetRipper to Run. 
<!-- NOTE: AssetRipper may be updated with a more Recent build which will Require .Net SDK 10 in the Future -->

## Unity Project Setup

1. In Unity at the Menubar go to **`Window > Package Manager`**.
2. Click the `+` button in the top left and choose **`Add package from git URL`**.
  ![Screenshot](/unity/0.png)
3. Paste all of the following Unity Packages one after another here:
  ![Screenshot](/unity/1.png)

  - **Unity Project Patcher:** Generates a Unity project from a game build so the game can be played in the editor.
    ```bash
    https://github.com/nomnomab/unity-project-patcher.git
    ```

  - **Unity Project Patcher BepInEx:** BepInEx handler for a Unity Project Patcher project.
    ```bash
    https://github.com/Kesomannen/unity-project-patcher-bepinex.git
    ```

  - **Unity Repo Project Patcher:** Game wrapper that generates a Unity project from R.E.P.O. build for in-editor play.
    ```bash
    https://github.com/ZehsTeam/unity-repo-project-patcher.git
    ```

### Patching the Project

1. After successfully adding the three packages above, navigate to the Unity menu bar and click on **`Tools > Unity Project Patcher > Configs > UPPatcherUserSettings`**.
    
    ![Screenshot](/unity/2.png)

2. You will now see new options in the **Inspector** panel. Leave all the pre-filled fields as they are and only add the games folder path.
    
    ![Screenshot](/unity/3.png)
    ![Screenshot](/unity/4.png)
    ![Screenshot](/unity/5.png)

3. Next, return to the Unity menu bar and click on **`Tools > Unity Project Patcher > Open Window`**.
    
    ![Screenshot](/unity/6.png)

4. In the newly opened **`UPPatcher - RepoWrapper`** window, click on **`Enable BepInEx`** and wait for the process to finish.
    
    ![Screenshot](/unity/7.png)

5. Once complete, click on **`Run Patcher`** to begin patching the project.
    
    ![Screenshot](/unity/8.png)
    
::: info NOTE
**This process WILL take a while and will restart the `Unity Editor` about 4-6 times.\
At the very beginning, you will receive `4` Popups. You can safely click `OK` on each of them.**
:::

6. After the Editor restarts for the final time, a confirmation window will appear indicating the project has been successfully patched. Click **`OK`**.
    
    ![Screenshot](/unity/9.png)

::: tip Troubleshooting
If you do not see this window, the patching process has failed. Check the Unity Console for more information.
:::

Now that you Unity Project is successfully patched, we recommend adding [the REPOLib-Sdk](./sdk/start.md) to your project workflow to make the Workflow easier.