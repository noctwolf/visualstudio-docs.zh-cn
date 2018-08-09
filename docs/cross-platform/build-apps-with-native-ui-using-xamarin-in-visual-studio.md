---
title: 在 Visual Studio 中使用 Xamarin 生成具有本机 UI 的应用 | Microsoft Docs
ms.custom: ''
ms.date: 03/30/2018
ms.technology: vs-ide-mobile
ms.topic: conceptual
ms.assetid: 30f137e6-595d-4ce7-b8f5-415b07c1caa2
author: charlespetzold
ms.author: chape
manager: crdun
ms.workload:
- xamarin
ms.openlocfilehash: 3475bfff07b64c171b506ff1cefaee6c8e55cdda
ms.sourcegitcommit: 495bba1d8029646653f99ad20df2f80faad8d58b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2018
ms.locfileid: "39381076"
---
# <a name="build-apps-with-native-ui-using-xamarin-in-visual-studio"></a>在 Visual Studio 中使用 Xamarin 生成具有本机 UI 的应用

选择 Xamarin 或 C# 编写跨平台移动应用程序的开发人员大多数都使用 Xamarin.Forms。 Xamarin.Forms 定义了一个用户界面，该用户界面可映射到 iOS、Android 和通用 Windows 平台 (UWP) 中的本机控件。 [学习在 Visual Studio 中使用 Xamarin.Forms 生成应用的基础知识](learn-app-building-basics-with-xamarin-forms-in-visual-studio.md)这篇文章介绍了 Xamarin.Forms。

该文章介绍了另一种涉及访问每个平台的本机用户接口 API 的方法。 由于要求广泛了解每个平台，使用本机 API 比使用 Xamarin.Forms 难得多。 但优点是可以根据每个平台的特定优势和功能定制用户界面，同时仍然可共享基础业务逻辑。

完成[设置和安装](../cross-platform/setup-and-install.md)以及[验证 Xamarin 环境](../cross-platform/verify-your-xamarin-environment.md)中的步骤后，此演示将介绍如何使用本机 UI 层生成基本 Xamarin 应用。 在本机 UI 中，共享代码驻留在 .NET Standard 库中，并且单个平台项目都包含 UI 定义。 以下是你将生成的应用程序，其运行平台从左到右依次为 iOS、Android phones 和 Windows 10 桌面。

![iOS、Android 和 Windows 上的 Xamarin 应用](../cross-platform/media/cross-plat-xamarin-build-1-Large.png#lightbox)

你将执行以下操作来生成它：

- [设置你的解决方案](#solution)

- [编写共享的数据服务代码](#dataservice)

- [适用于 Android 的设计 UI](#Android)

- [设计适用于 Windows 的 UI](#Windows)

- [后续步骤](#next)，包括设计 iOS 用户界面

> [!TIP]
> 可在 [GitHub 上的 mobile-samples 存储库](https://github.com/xamarin/mobile-samples/tree/master/Weather)中找到此项目的完整源代码。
>
> 如果你遇到任何困难或错误，请将问题发布在 [forums.xamarin.com](http://forums.xamarin.com)。 通过更新至 Xamarin 所需的最新 SDK，可解决许多问题，每个平台的 [Xamarin 发行说明](https://developer.xamarin.com/releases/)中对这些 SDK 进行了描述。

> [!NOTE]
> Xamarin 的开发人员文档还通过下列“快速入门”和“深入了解”部分提供了一些演练。 在所有这些页面上，请务必选择“Visual Studio”以查看特定于 Visual Studio 的演练。
>
>  -   具有本机 UI 的 Xamarin 应用程序：
>     -   [Hello，Android](/xamarin/android/get-started/hello-android/) （具有单个屏幕的简单应用）
>     -   [Hello，Android 多屏显示](/xamarin/android/get-started/hello-android-multiscreen/) （可在屏幕之间导航的应用）
>     -   [Android 片段演练](/xamarin/android/platform/fragments/implementing-with-fragments/) （用于主屏幕/详细信息屏幕等）
>     -   [Hello，iOS](/xamarin/ios/get-started/hello-iOS/)
>     -   [Hello，iOS 多屏显示](/xamarin/ios/get-started/hello-iOS-multiscreen/)

>  -   具有 Xamarin.Forms（共享 UI）的 Xamarin 应用
>     -   [Hello，Xamarin.Forms](/xamarin/xamarin-forms/get-started/hello-xamarin-forms/quickstart/)
>     -   [了解 Xamarin.Forms 多屏显示](/xamarin/xamarin-forms/get-started/hello-xamarin-forms-multiscreen/)

<a name="solution" />

##  <a name="set-up-your-solution"></a>设置你的解决方案

Visual Studio 没有解决方案模板用于创建共享 .NET Standard 库的本机 UI 应用程序。 但从单个项目生成这样的解决方案并不难。 以下步骤使用项目为每种类型的应用程序平台创建 Xamarin 解决方案，并为共享代码创建 .NET Standard 库。

1.  在 Visual Studio 中，创建新的“类库 (.NET Standard)”解决方案，并将其命名为“WeatherApp”。 通过在左侧依次选择“Visual C#”和“.NET Standard”，可以最为轻松地找到此模板：

    ![创建 .NET Standard 解决方案](../cross-platform/media/cross-plat-xamarin-build-2.png)

    在单击“确定”后，名为“WeatherApp”的单个项目将组成“WeatherApp”解决方案。

2.  若要面向 iOS，请将 iOS 项目添加到此解决方案。 在解决方案资源管理器中右键单击解决方案名称，然后选择“添加”和“新建项目”。  在“新建项目”对话框的左侧选择“Visual C#”，然后选择“iOS”和“通用”。 （如果找不到，建议安装 Xamarin 或启用 Visual Studio 2017 功能，请参阅[设置和安装](../cross-platform/setup-and-install.md)。）在模板列表中，选择“单一视图应用(iOS)”。 将它命名为“WeatherApp.iOS”。

3.  若要面向 Android，请将 Android 项目添加到此解决方案。 在“新建项目”对话框的左侧选择“Visual C#”和“Android”。 在模板列表中，选择“空白应用(Android)”。 将它命名为“WeatherApp.Android”。

4. 若要面向通用 Windows 平台，请在“新建项目”对话框的左侧选择“Visual C#”和“Windows 通用”。 在模板列表中，选择“空白应用(通用 Windows)”并将它命名为“WeatherApp.UWP”。

5. 对于每个应用程序项目（iOS、Android 和 UWP），在解决方案资源管理器中，右键单击“引用”部分，然后选择“添加引用”。 在“引用管理器”对话框的左侧选择“项目”和“解决方案”。 在解决方案中将看到所有项目的列表，引用正在被管理的项目除外：

   ![设置对 .NET Standard 项目的引用](../cross-platform/media/cross-plat-xamarin-build-3.png)

   选中“WeatherApp”旁边的复选框。

   在为每个应用程序项目选中此复选框后，所有项目都包含对 .NET Standard 库的引用并可以在此库中共享代码。

6. 将“Newtonsoft.Json”NuGet 包添加到 .NET Standard 项目中，用于处理从天气数据服务中检索到的信息：

    -   在解决方案资源管理器中，右键单击“WeatherApp”，然后选择“管理 NuGet 包...”。

         在 NuGet 窗口中，选择“浏览”选项卡，然后搜索“Newtonsoft”。

    -   选择 **Newtonsoft.Json**。

    -   确保“版本”  字段设置为“最新稳定”  版本。

    -   单击“安装” 。

7.  重复步骤 6 找到“Microsoft.CSharp”包并将其安装在 .NET Standard 项目中。 在 .NET Standard 库中使用 C# `dynamic` 数据类型时，需要此库。

8.  生成解决方案并验证没有生成错误。

<a name="dataservice" />

## <a name="write-shared-data-service-code"></a>编写共享的数据服务代码

 “WeatherApp”项目为 .NET Standard 库。 在所有平台上共享的代码将在此项目中编写。 由于每个应用程序项目都有对 .NET Standard 库的引用，因此 iOS、Android 和 UWP 应用包都包含该库。

 执行以下步骤，将代码添加到 .NET Standard 库，以访问和存储天气服务中的数据：

1.  首先在 [http://openweathermap.org/appid](http://openweathermap.org/appid) 注册，获取免费的天气 API 密钥。 此 API 密钥允许应用程序获取任何美国邮政编码对应的天气。 （它并不适用于美国以外的邮政编码。）

2.  右键单击“WeatherApp”项目，然后选择“添加”>“类…”。在“添加新项”  对话框中，将文件命名为 *Weather.cs*。 将使用此类来存储天气数据服务的数据。

3.  将 Weather.cs 的全部内容替换为以下代码：

    ```csharp
    namespace WeatherApp
    {
        public class Weather
        {
            // Because labels bind to these values, set them to an empty string to
            // ensure that the label appears on all platforms by default.
            public string Title { get; set; } = " ";
            public string Temperature { get; set; } = " ";
            public string Wind { get; set; } = " ";
            public string Humidity { get; set; } = " ";
            public string Visibility { get; set; } = " ";
            public string Sunrise { get; set; } = " ";
            public string Sunset { get; set; } = " ";
        }
    }
    ```

4.  将另一个类添加到名为 `DataService.cs` 的 .NET Standard 项目中。 此类将用于从天气数据服务处理 JSON 数据。

5.  将 *DataService.cs* 的全部内容替换为以下代码：

    ```csharp
    using System.Net.Http;
    using System.Threading.Tasks;
    using Newtonsoft.Json;

    namespace WeatherApp
    {
        public class DataService
        {
            public static async Task<dynamic> GetDataFromService(string queryString)
            {
                HttpClient client = new HttpClient();
                var response = await client.GetAsync(queryString);

                dynamic data = null;
                if (response != null)
                {
                    string json = response.Content.ReadAsStringAsync().Result;
                    data = JsonConvert.DeserializeObject(json);
                }

                return data;
            }
        }
    }
    ```

6.  将第三个类添加到名为 Core.cs 的 .NET Standard 库中。 此类将用于形成包含邮政编码的查询字符串、调用天气数据服务和填充 Weather 类实例。

7.  将 Core.cs 的内容替换为以下代码：

    ```csharp
    using System;
    using System.Threading.Tasks;

    namespace WeatherApp
    {
        public class Core
        {
            public static async Task<Weather> GetWeather(string zipCode)
            {
                //Sign up for a free API key at http://openweathermap.org/appid
                string key = "YOUR API KEY HERE";
                string queryString = "http://api.openweathermap.org/data/2.5/weather?zip="
                    + zipCode + ",us&appid=" + key + "&units=imperial";

                //Make sure developers running this sample replaced the API key
                if (key == "YOUR API KEY HERE")
                {
                    throw new ArgumentException("You must obtain an API key from openweathermap.org/appid and save it in the 'key' variable.");
                }

                dynamic results = await DataService.GetDataFromService(queryString).ConfigureAwait(false);

                if (results["weather"] != null)
                {
                    Weather weather = new Weather();
                    weather.Title = (string)results["name"];
                    weather.Temperature = (string)results["main"]["temp"] + " F";
                    weather.Wind = (string)results["wind"]["speed"] + " mph";
                    weather.Humidity = (string)results["main"]["humidity"] + " %";
                    weather.Visibility = (string)results["weather"][0]["main"];

                    DateTime time = new System.DateTime(1970, 1, 1, 0, 0, 0, 0);
                    DateTime sunrise = time.AddSeconds((double)results["sys"]["sunrise"]);
                    DateTime sunset = time.AddSeconds((double)results["sys"]["sunset"]);
                    weather.Sunrise = sunrise.ToString() + " UTC";
                    weather.Sunset = sunset.ToString() + " UTC";
                    return weather;
                }
                else
                {
                    return null;
                }
            }
        }
    }
    ```

8. 使用在步骤 1 中获得的 API 密钥替换第一次出现的“在此处输入你的 API 密钥”。 仍需使用引号将其引起来！

9. 删除 .NET Standard 库中的 MyClass.cs，因为不会用到它。

10. 生成 WeatherApp 项目，以确保代码正确无误。

<a name="Android" />

## <a name="design-ui-for-android"></a>设计适用于 Android 的 UI

 现在，你将设计用户界面，将其连接到你的共享代码，然后运行此应用。

### <a name="design-the-look-and-feel-of-your-app"></a>设计应用的外观和感觉

1.  在解决方案资源管理器中，展开“WeatherApp.Droid”>“资源”>“布局”文件夹，然后打开“Main.axml”。 此命令可在可视化设计器中打开此文件。 （如果出现与 Java 相关的错误，请参阅此[博客文章](http://forums.xamarin.com/discussion/32365/connection-to-the-layout-renderer-failed-in-xs-5-7-and-xamarinvs-3-9)。）

    > [!TIP]
    >  项目中有许多其他文件。 对它们的探讨不在本文范围内，但如果要深入了解 Android 项目的结构，请参阅“Hello Android”一文的[第 2 部分：深入了解](/xamarin/android/get-started/hello-android/hello-android-deepdive/)。

2.  通过“视图”>“其他窗口”>“工具箱”，打开此工具箱。

3.  从 **“工具箱”**，将 **“RelativeLayout”** 控件拖动到设计器。 可将此控件用作其他控件的父容器。

    > [!TIP]
    >  如果布局显示不正确，请保存文件，然后通过在“设计”和“源”选项卡之间进行切换来刷新。

4.  在“属性”窗口中，将“background”属性（在“样式”组中）设置为 `#545454`。  通过你设置“RelativeLayout”的背景所在的“属性”窗口中的标题进行确认。

5.  从 **“工具箱”**，将 **“TextView”** 控件拖动到 **“RelativeLayout”** 控件上。

6.  在“属性”窗口中，设置这些属性。 （它有助于使用“属性”窗口工具栏中的排序按钮对列表进行按字母顺序排序）：

    |属性|“值”|
    |--------------|-----------|
    |**text**|**根据“邮政编码”进行搜索**|
    |**id**|`@+id/ZipCodeSearchLabel`|
    |**layout_marginStart**|`10dp`|
    |**textColor**|`@android:color/white`|
    |**textStyle**|`bold`|

    > [!TIP]
    >  请注意，许多属性不包含可选值的下拉列表。  可能难以猜测给定属性适用于什么样的字符串值。 有关建议，请尝试在 [`R.attr`](http://developer.android.com/reference/android/R.attr.html) 类页面中搜索属性的名称。
    >
    >  此外，快速 Web 搜索通常指向 [http://stackoverflow.com/](http://stackoverflow.com/) 上的页面，在这里其他人使用相同的属性。

     对于引用，如果切换到“源”视图，则应看到此元素的以下代码：

    ```xml
    <TextView
        android:text="Search by Zip Code"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:id="@+id/ZipCodeSearchLabel"
        android:layout_marginStart="10dp"
        android:textColor="@android:color/white"
        android:textStyle="bold" />

    ```

7.  在“工具箱”中，将“TextView”控件拖动到“RelativeLayout”控件上，然后将其放置在 ZipCodeSearchLabel 控件下。 将新控件放置在现有控件的相应边缘上。 它可以帮助将设计器放大到一定程度以放置控件。

8. 在 **“属性”** 窗口中，设置以下属性：

    |属性|“值”|
    |--------------|-----------|
    |**文本**|**“邮政编码”**|
    |**id**|`@+id/ZipCodeLabel`|
    |**layout_marginStart**|`10dp`|
    |**layout_marginTop**|`6dp`|
    |**textColor**|`@android:color/white`|

    “源”视图中的代码应类似于下方所示：

    ```xml
    <TextView
        android:text="Zip Code"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@id/ZipCodeSearchLabel"
        android:id="@+id/ZipCodeLabel"
        android:layout_marginStart="10dp"
        android:layout_marginTop="6dp"
        android:textColor="@android:color/white" />
    ```

9. 在“工具箱”中，将“数字”控件拖动到“RelativeLayout”上，然后将其放置在“邮政编码”标签下。 然后设置以下属性：

    |属性|“值”|
    |--------------|-----------|
    |**id**|`@+id/zipCodeEntry`|
    |**layout_marginStart**|`10dp`|
    |**layout_marginBottom**|`10dp`|
    |**width**|`165dp`|
    |**textColor**|`@android:color/white`|

    用户将在“数字”控件处键入五位数的美国邮政编码。 以下是与该控件相对应的标记：

    ```xml
    <EditText
        android:inputType="number"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@id/ZipCodeLabel"
        android:id="@+id/zipCodeEntry"
        android:layout_marginStart="10dp"
        android:layout_marginBottom="10dp"
        android:width="165dp"
        android:textColor="@android:color/white" />
    ```

10. 在“工具箱”中，将“按钮”拖动到“RelativeLayout”控件上，然后将其放置在 zipCodeEntry 控件的右侧。 然后设置这些属性：

    |属性|“值”|
    |--------------|-----------|
    |**id**|`@+id/weatherBtn`|
    |**文本**|**获取天气信息**|
    |**layout_marginStart**|`20dp`|
    |**layout_alignBottom**|`@id/zipCodeEntry`|
    |**width**|`165dp`|

    ```xml
    <Button
        android:text="Get Weather"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_toRightOf="@id/zipCodeEntry"
        android:id="@+id/weatherBtn"
        android:layout_marginStart="20dp"
        android:layout_alignBottom="@id/zipCodeEntry"
        android:width="165dp" />
    ```

11. 你通过使用 Android 设计器，现已充分了解如何生成基本 UI。 也可通过将标记直接添加到页面的 Main.axml 文件来生成 UI。 要以这种方式生成其余的 UI，请在设计器中切换到“源”视图，然后将以下标记粘贴到 `</RelativeLayout>` 结束标记下方。 （它们必须在标记下方，因为 `RelativeLayout` 不包含这些元素。）

    ```xml
    <TextView
        android:text="Location"
        android:textAppearance="?android:attr/textAppearanceSmall"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/locationLabel"
        android:layout_marginStart="10dp"
        android:layout_marginTop="10dp" />
    <TextView
        android:textAppearance="?android:attr/textAppearanceMedium"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/locationText"
        android:layout_marginStart="20dp"
        android:layout_marginBottom="10dp" />
    <TextView
        android:text="Temperature"
        android:textAppearance="?android:attr/textAppearanceSmall"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/tempLabel"
        android:layout_marginStart="10dp" />
    <TextView
        android:textAppearance="?android:attr/textAppearanceMedium"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/tempText"
        android:layout_marginBottom="10dp"
        android:layout_marginStart="20dp" />
    <TextView
        android:text="Wind Speed"
        android:textAppearance="?android:attr/textAppearanceSmall"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/windLabel"
        android:layout_marginStart="10dp" />
    <TextView
        android:textAppearance="?android:attr/textAppearanceMedium"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/windText"
        android:layout_marginBottom="10dp"
        android:layout_marginStart="20dp" />
    <TextView
        android:text="Humidity"
        android:textAppearance="?android:attr/textAppearanceSmall"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/humidtyLabel"
        android:layout_marginStart="10dp" />
    <TextView
        android:textAppearance="?android:attr/textAppearanceMedium"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/humidityText"
        android:layout_marginBottom="10dp"
        android:layout_marginStart="20dp" />
    <TextView
        android:text="Visibility"
        android:textAppearance="?android:attr/textAppearanceSmall"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/visibilityLabel"
        android:layout_marginStart="10dp" />
    <TextView
        android:textAppearance="?android:attr/textAppearanceMedium"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/visibilityText"
        android:layout_marginBottom="10dp"
        android:layout_marginStart="20dp" />
    <TextView
        android:text="Time of Sunrise"
        android:textAppearance="?android:attr/textAppearanceSmall"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/sunriseLabel"
        android:layout_marginStart="10dp" />
    <TextView
        android:textAppearance="?android:attr/textAppearanceMedium"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/sunriseText"
        android:layout_marginBottom="10dp"
        android:layout_marginStart="20dp" />
    <TextView
        android:text="Time of Sunset"
        android:textAppearance="?android:attr/textAppearanceSmall"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/sunsetLabel"
        android:layout_marginStart="10dp" />
    <TextView
        android:textAppearance="?android:attr/textAppearanceMedium"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/sunsetText"
        android:layout_marginBottom="10dp"
        android:layout_marginStart="20dp" />
    ```

12. 保存该文件，然后切换到“设计”视图。 你的 UI 应如下显示：

     ![Android 应用程序的 UI](../cross-platform/media/xamarin_androidui.png)

13. 打开“MainActivity.cs”。 此代码应如下方所示：

    ```csharp
    protected override void OnCreate (Bundle bundle)
    {
        base.OnCreate (bundle);

        // Set our view from the "main" layout resource
        SetContentView (Resource.Layout.Main);
    }
    ```

14. 生成 Android 项目以检查工作。 此生成过程会将控件 ID 添加到“Resource.Designer.cs”文件，以便你可在代码中根据名称引用控件。

### <a name="consume-your-shared-code"></a>使用你的共享代码

1.  在代码编辑器中打开“WeatherApp”项目的“MainActivity.cs”文件，然后将其内容替换为下面的代码。 此代码调用你在共享代码中定义的 `GetWeather` 方法。 在应用的 UI 中，将显示从此方法中检索的数据。

    ```csharp
    using System;
    using Android.App;
    using Android.Widget;
    using Android.OS;

    namespace WeatherApp.Droid
    {
        [Activity(Label = "Sample Weather App",
                  Theme = "@android:style/Theme.Material.Light",
                  MainLauncher = true)]
        public class MainActivity : Activity
        {
            protected override void OnCreate(Bundle bundle)
            {
                base.OnCreate(bundle);

                SetContentView(Resource.Layout.Main);

                Button button = FindViewById<Button>(Resource.Id.weatherBtn);

                button.Click += Button_Click;
            }

            private async void Button_Click(object sender, EventArgs e)
            {
                EditText zipCodeEntry = FindViewById<EditText>(Resource.Id.zipCodeEntry);

                if (!String.IsNullOrEmpty(zipCodeEntry.Text))
                {
                    Weather weather = await Core.GetWeather(zipCodeEntry.Text);
                    FindViewById<TextView>(Resource.Id.locationText).Text = weather.Title;
                    FindViewById<TextView>(Resource.Id.tempText).Text = weather.Temperature;
                    FindViewById<TextView>(Resource.Id.windText).Text = weather.Wind;
                    FindViewById<TextView>(Resource.Id.visibilityText).Text = weather.Visibility;
                    FindViewById<TextView>(Resource.Id.humidityText).Text = weather.Humidity;
                    FindViewById<TextView>(Resource.Id.sunriseText).Text = weather.Sunrise;
                    FindViewById<TextView>(Resource.Id.sunsetText).Text = weather.Sunset;
                }
            }
        }
    }
    ```

    请注意，活动已给定浅色背景主题。

### <a name="run-the-app-and-see-how-it-looks"></a>运行此应用，查看其外观

1.  在“解决方案资源管理器”中，请确保将“WeatherApp.Droid”项目设为启动项目。

2.  选择合适的设备或仿真器目标，然后按 F5 键启动该应用。

    > [!NOTE]
    > 如果 Visual Studio 指示 Android 项目找不到 Newtonsoft.Json 文件，请将该 NuGet 包添加到 Android 项目。

3.  在设备上或在仿真器中，将有效的美国五位数邮政编码键入编辑框，然后按“获取天气信息”。 然后，控件中将显示此区域的天气数据。

    [![Android 上的 Xamarin 应用](../cross-platform/media/cross-plat-xamarin-build-1-android.png)](../cross-platform/media/cross-plat-xamarin-build-1-android-Large.png#lightbox)

> [!TIP]
>  可在 [GitHub 上的 mobile-samples 存储库](https://github.com/xamarin/mobile-samples/tree/master/Weather)中找到此项目的完整源代码。

<a name="Windows" />

## <a name="design-ui-for-windows"></a>设计适用于 Windows 的 UI

后续步骤是设计 Windows 的用户界面，将其连接到你的共享代码，然后运行应用。

### <a name="design-the-look-and-feel-of-your-app"></a>设计应用的外观和感觉

 在 Xamarin 应用中设计本机 UWP 用户界面的过程不同于任何其他本机 UWP 应用。 因此，此处不讨论设计器的使用。 有关详细讨论，请参阅[使用 XAML 设计器创建 UI](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md)。

 而是打开“MainPage.xaml”并使用以下标记替换整个 XAML 内容：

```xaml
<Page
    x:Class="WeatherApp.UWP.MainPage"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:local="using:WeatherApp.UWP"
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
    mc:Ignorable="d">

    <Grid Background="{ThemeResource ApplicationPageBackgroundThemeBrush}">

        <StackPanel HorizontalAlignment="Left"
                    VerticalAlignment="Top"
                    Height="40" Margin="10,0,0,0" Width="400">
            <TextBlock Text="Weather App" FontSize="30" />
        </StackPanel>
        <StackPanel HorizontalAlignment="Left"
                    VerticalAlignment="Top"
                    Height="120" Margin="10,40,0,0" Width="400"
                    Background="#FF545454">

            <TextBlock Text="Search by Zip Code" TextWrapping="Wrap"
                       HorizontalAlignment="Left" Margin="10,10,0,0"
                       Foreground="White" FontSize="18" FontWeight="Bold" />

            <TextBlock Text="Zip Code" TextWrapping="Wrap"
                       Margin="10,5,0,0" FontSize="14" Foreground="#FFA8A8A8"/>

            <StackPanel Orientation="Horizontal">

                <TextBox x:Name="zipCodeEntry" Text=""
                         Margin="10,10,0,0" VerticalAlignment="Top"
                         InputScope="Number" Width="165" />

                <Button x:Name="weatherBtn" Content="Get Weather"
                        Foreground="White" Width="165" Margin="20,0,0,0" Height="60"
                        Click="GetWeatherButton_Click"/>
            </StackPanel>
        </StackPanel>

        <StackPanel Margin="10,175,0,0">
            <StackPanel.Resources>
                <Style x:Key="commonText" TargetType="TextBlock">
                    <Setter Property="HorizontalAlignment" Value="Left" />
                    <Setter Property="VerticalAlignment" Value="Top" />
                    <Setter Property="TextWrapping" Value="Wrap" />
                </Style>

                <Style x:Key="labelText" TargetType="TextBlock" BasedOn="{StaticResource commonText}">
                    <Setter Property="FontSize" Value="14" />
                    <Setter Property="Foreground" Value="#FFA8A8A8" />
                </Style>

                <Style x:Key="valueText" TargetType="TextBlock" BasedOn="{StaticResource commonText}">
                    <Setter Property="FontSize" Value="18" />
                    <Setter Property="Margin" Value="10, 0, 0, 10" />
                </Style>
            </StackPanel.Resources>

            <TextBlock Text="Location" Style="{StaticResource labelText}" />
            <TextBlock x:Name="locationText" Style="{StaticResource valueText}" />

            <TextBlock Text="Temperature" Style="{StaticResource labelText}" />
            <TextBlock x:Name="tempText" Style="{StaticResource valueText}" />

            <TextBlock Text="Wind Speed" Style="{StaticResource labelText}" />
            <TextBlock x:Name="windText" Style="{StaticResource valueText}" />

            <TextBlock Text="Humidity" Style="{StaticResource labelText}" />
            <TextBlock x:Name="humidityText" Style="{StaticResource valueText}" />

            <TextBlock Text="Temperature" Style="{StaticResource labelText}" />
            <TextBlock x:Name="visibilityText" Style="{StaticResource valueText}" />

            <TextBlock Text="Time of Sunrise" Style="{StaticResource labelText}" />
            <TextBlock x:Name="sunriseText" Style="{StaticResource valueText}" />

            <TextBlock Text="Time of Sunset" Style="{StaticResource labelText}" />
            <TextBlock x:Name="sunsetText" Style="{StaticResource valueText}" />
        </StackPanel>
    </Grid>
</Page>
```

### <a name="consume-your-shared-code"></a>使用你的共享代码

在“MainPage.xaml.cs”代码隐藏文件中，为按钮添加以下事件处理程序：

```csharp
private async void GetWeatherButton_Click(object sender, RoutedEventArgs e)
{
    if (!String.IsNullOrEmpty(zipCodeEntry.Text))
    {
        Weather weather = await Core.GetWeather(zipCodeEntry.Text);
        locationText.Text = weather.Title;
        tempText.Text = weather.Temperature;
        windText.Text = weather.Wind;
        visibilityText.Text = weather.Visibility;
        humidityText.Text = weather.Humidity;
        sunriseText.Text = weather.Sunrise;
        sunsetText.Text = weather.Sunset;

        weatherBtn.Content = "Search Again";
    }
}
```

此代码调用你在共享代码中定义的 `GetWeather` 方法。 `GetWeather` 是你在 Android 应用中调用的同一个方法。 此代码还显示从你应用的 UI 控件中的方法检索的数据。

### <a name="run-the-app-and-see-how-it-looks"></a>运行此应用，查看其外观

1.  在解决方案资源管理器中，将“WeatherApp.UWP”项目设置为启动项目。

2.  在“解决方案平台”下拉框中，选择“x86”，并选择“本地计算机”将应用程序部署到 Windows 10 桌面。

3.  按 F5 键，启动此应用。

4.  将有效的五位数美国邮政编码键入到编辑框，然后按“获取天气信息”。 然后，页面中将显示此区域的天气数据。

    [![UWP 上的 Xamarin 应用](../cross-platform/media/cross-plat-xamarin-build-1-uwp.png)](../cross-platform/media/cross-plat-xamarin-build-1-uwp-Large.png#lightbox)

> [!TIP]
>  可在 [GitHub 上的 mobile-samples 存储库](https://github.com/xamarin/mobile-samples/tree/master/Weather)中找到此项目的完整源代码。

<a name="next" />

## <a name="next-steps"></a>后续步骤

 **将适用于 iOS 的 UI 添加到解决方案**

 通过添加适用于 iOS 的本机 UI 来扩展此示例。 要测试 iOS 上的代码，请连接到本地网络上安装了 Xcode 和 Xamarin 的 Mac。 连接后，可直接在 Visual Studio 中使用 iOS 设计器。 有关已完成的应用，请参阅 [GitHub 上的 mobile-samples 存储库](https://github.com/xamarin/mobile-samples/tree/master/Weather)。

 另请参阅 [Hello, iOS](/xamarin/ios/get-started/hello-ios/hello-ios-quickstart?tabs=vswin) 演练。

 **在共享项目中添加特定于平台的代码**

 .NET Standard 库中的共享代码与平台无关。 库在编译后，便会包含在每个特定于平台的应用包中。 若要编写使用条件编译的共享代码来分离特定于平台的代码，可使用共享项目。 有关详细信息，请参阅[代码共享选项](/xamarin/cross-platform/app-fundamentals/building-cross-platform-applications/practical-code-sharing-strategies)。

## <a name="see-also"></a>请参阅

- [Xamarin 文档](http://docs.microsoft.com/xamarin)
- [Windows 开发人员中心](https://dev.windows.com/en-us)
- [Swift 与 C# 快速参考海报](http://aka.ms/scposter)
