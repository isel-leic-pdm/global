# ComposeExamples

This project contains the source code presented in the set of slides for the course. It is located in the `demos/ComposeExamples` directory relative to the repository root.

## Code and Slides Mapping

The corresponding slides are located in the [`slides`](../../slides) directory at the repository root:

* **Activity**: [`MainActivity.kt`](app/src/main/java/prodigi/pdm/demos/compose/MainActivity.kt) (demonstrating `ComponentActivity` and basic setup)  
  Presented in [PDM - 03 - Activity.pdf](../../slides/PDM%20-%2003%20-%20Activity.pdf)
* **Compose Introduction**: [`MainActivity.kt`](app/src/main/java/prodigi/pdm/demos/compose/MainActivity.kt) and [`Greeting.kt`](app/src/main/java/prodigi/pdm/demos/compose/Greeting.kt)  
  Presented in [PDM - 04 - Compose (Introdução).pdf](../../slides/PDM%20-%2004%20-%20Compose%20%28Introduc%CC%A7a%CC%83o%29.pdf)
* **Compose Layouts**: Composables in the [`layouts`](app/src/main/java/prodigi/pdm/demos/compose/layouts) package (`BottomSheetDemo.kt`, `BoxDemo.kt`, `CarroselDemo.kt`, `ColumnDemo.kt`, `GridDemo.kt`, `LazyColumnDemo.kt`, `NavigationDrawerDemo.kt`, `RowWeightDemo.kt`, `ScaffoldDemoBottomBar.kt`, `ScaffoldDemoTopBar.kt`, `TabRowDemo.kt`)  
  Presented in [PDM - 05 - Compose (Layouts).pdf](../../slides/PDM%20-%2005%20-%20Compose%20%28Layouts%29.pdf)
* **Compose State**: [`LoginActivity.kt`](app/src/main/java/prodigi/pdm/demos/compose/state/LoginActivity.kt) and [`LoginForm.kt`](app/src/main/java/prodigi/pdm/demos/compose/state/LoginForm.kt)  
  Presented in [PDM - 06 - Compose (Estado).pdf](../../slides/PDM%20-%2006%20-%20Compose%20%28Estado%29.pdf)
* **Concurrency in Compose**: [`CoroutinesFunActivity.kt`](app/src/main/java/prodigi/pdm/demos/compose/coroutinesfun/CoroutinesFunActivity.kt)  
  Presented in [PDM - 07 - Concorrência.pdf](../../slides/PDM%20-%2007%20-%20Concorre%CC%82ncia.pdf)

---

## How to Execute the Activities

Because this project includes multiple `Activity` implementations demonstrating distinct Jetpack Compose topics, you can launch a specific Activity using any of the following methods:

### Method 1: Specify Activity in Android Studio Run Configuration (Recommended)

1. In Android Studio, select **Run** > **Edit Configurations...** from the top menu.
2. Under **Android App**, select the **app** configuration.
3. In the **General** tab, set **Launch Options** > **Launch** from *Default Activity* to **Specified Activity**.
4. In the **Activity** field, choose or type the desired Activity class:
   * `prodigi.pdm.demos.compose.MainActivity`
   * `prodigi.pdm.demos.compose.state.LoginActivity`
   * `prodigi.pdm.demos.compose.coroutinesfun.CoroutinesFunActivity`
5. Click **Apply** and **OK**, then run the application (`Shift + F10` / `Control + R`).

---

### Method 2: Add Launcher Intent Filter in `AndroidManifest.xml`

You can set an Activity as the default launcher Activity by moving the `<intent-filter>` block in [`AndroidManifest.xml`](app/src/main/AndroidManifest.xml):

1. Open [`app/src/main/AndroidManifest.xml`](app/src/main/AndroidManifest.xml).
2. Ensure `android:exported="true"` is set on the Activity tag.
3. Move the `MAIN` and `LAUNCHER` intent filter to that Activity:

```xml
<activity
    android:name=".state.LoginActivity"
    android:exported="true">
    <intent-filter>
        <action android:name="android.intent.action.MAIN" />
        <category android:name="android.intent.category.LAUNCHER" />
    </intent-filter>
</activity>
```

4. Build and run the project normally.

---

### Method 3: Compose Previews

Individual layout and state composables can also be inspected directly inside Android Studio without running on a device or emulator. Open the source file and view the `@Preview` composables using the **Split** or **Design** editor view.
