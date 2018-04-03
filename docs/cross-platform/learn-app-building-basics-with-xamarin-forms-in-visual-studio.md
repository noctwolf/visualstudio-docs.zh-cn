---
title: 学习在 Visual Studio 中使用 Xamarin.Forms 生成应用的基础知识 | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2018
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d22b5186-9e03-4e85-afc9-7cbe28522a6d
ms.technology: vs-ide-mobile
author: charlespetzold
ms.author: chape
manager: crdun
ms.workload:
- xamarin
ms.openlocfilehash: 6c0659e63feb685f002b7be969ee827e5e047cdd
ms.sourcegitcommit: fb1fede41d8c5e459dd222755b0497b9d361bc51
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2018
---
# <a name="learn-app-building-basics-with-xamarinforms-in-visual-studio"></a>学习在 Visual Studio 中使用 Xamarin.Forms 生成应用的基础知识

完成 [Setup and install](../cross-platform/setup-and-install.md) 和 [Verify your Xamarin environment](../cross-platform/verify-your-xamarin-environment.md)中的步骤后，此演练会立即演示如何借助 Xamarin.Forms 生成基本应用（如下所示）。 借助 Xamarin.Forms，可以在 .NET Standard 类库中一次性编写全部 UI 代码。 随后，Xamarin 会自动呈现 iOS、Android 和通用 Windows 平台的本机 UI 控件。 建议使用此方法（而不是共享项目），因为 .NET Standard 库仅包含跨所有目标平台受支持的 .NET API，并且 Xamarin.Forms 支持跨平台共享 UI 代码。  
  
![Android、iOS 和 Windows 上的“天气”应用示例](../cross-platform/media/crossplat-xamarin-formsguide-1.png "CrossPlat Xamarin FormsGuide 1")  
  
你将执行以下操作来生成它：  
  
-   [设置你的解决方案](#solution)  
  
-   [编写共享的数据服务代码](#dataservice)  
  
-   [开始编写共享的 UI 代码](#uicode)  
  
-   [使用适用于 Android 的 Visual Studio 仿真程序测试你的应用。](#test)  
  
-   [跨平台完成具有本机外观的 UI](#finish)  
  
> [!TIP]
> 可以在 [xamarin-forms-samples repository on GitHub](https://github.com/xamarin/xamarin-forms-samples/tree/master/Weather)（GitHub 上的 xamarin-forms-samples 存储库）中找到此项目完整的源代码。  
  
##  <a name="solution"></a> 设置你的解决方案  

按照下面这些步骤操作可以创建 Xamarin.Forms 解决方案，其中包含共享代码的 .NET Standard 类库和两个添加的 NuGet 包。  
  
1.  在 Visual Studio 中，新建“跨平台应用 (Xamarin.Forms)”解决方案，并将它命名为“WeatherApp”。 在左侧列表中依次选择“Visual C#”和“跨平台”，以查找模板。  
  
     如果找不到，建议安装 Xamarin 或启用 Visual Studio 2017 功能（请参阅[设置和安装](../cross-platform/setup-and-install.md)）。  
  
     ![新建空白应用“跨平台应用 (Xamarin.Forms)”项目](../cross-platform/media/crossplat-xamarin-formsguide-2.png "CrossPlat Xamarin FormsGuide 2")

2.  单击“确定”后，可以选择一些选项。 选取“空白应用”、“Xamarin.Forms”和“.NET Standard”：

     ![新建跨平台应用项目](../cross-platform/media/crossplat-xamarin-formsguide-3.png "CrossPlat Xamarin FormsGuide 3")
  
3.  单击“确定”创建解决方案后，将会得到多个单独项目：  
  
    -   **WeatherApp**：.NET Standard 库，可以在其中编写跨平台共享的代码，包括使用 Xamarin.Forms 的常见业务逻辑和 UI 代码。  
  
    -   **WeatherApp.Android**：包含本机 Android 代码的项目。 这将设置为默认启动项目。  
  
    -   **WeatherApp.iOS**：包含本机 iOS 代码的项目。  
  
    -   **WeatherApp.UWP**：包含 Windows 10 UWP 代码的项目。  
  
    > [!NOTE]
    >  可随意删除你不准备面向的目标平台的任何项目。   
  
     在每个本机项目中，你有权访问相应平台的本机设计器，并且可以根据需要实现特定于平台的屏幕和功能。  
  
4.  将解决方案中的 Xamarin.Forms NuGet 包升级到最新稳定版本，如下所示。 我们建议每次创建新 Xamarin 解决方案时执行此操作：  
  
    -   选择“工具”>“NuGet 包管理器”>“管理解决方案的 NuGet 包”。  
  
    -   在“更新”选项卡下，选中“Xamarin.Forms”包，并选中解决方案中的所有项目以供更新。 （注意：不要选中 Xamarin.Android.Support 的任何更新。）  
  
    -   将“版本”  字段更新为可用的“最新稳定”  版本。  
  
    -   单击“安装” 。  
  
         ![更新 Xamarin.Forms NuGet 包](../cross-platform/media/crossplat-xamarin-formsguide-4.png "CrossPlat Xamarin FormsGuide 4")  
  
5.  将 Newtonsoft.Json NuGet 包添加到 WeatherApp 项目中，用于处理从天气数据服务中检索到的信息：  
  
    -   在 NuGet 包管理器中（自第 4 步起仍处于打开状态），选择“浏览”选项卡，再搜索“Newtonsoft”。  
  
    -   选择 **Newtonsoft.Json**。  
  
    -   检查 **weatherapp** 项目（这是唯一需要安装包的项目）。  
  
    -   确保“版本”  字段设置为“最新稳定”  版本。  
  
    -   单击“安装” 。  
  
    ![查找和安装 Newtonsoft.Json NuGet 包](../cross-platform/media/crossplat-xamarin-formsguide-5.png "CrossPlat Xamarin FormsGuide 5")  
  
6.  重复执行第 5 步，查找并安装“Microsoft.Net.Http”包。  
  
7.  生成解决方案并验证没有生成错误。  
  
##  <a name="dataservice"></a> 编写共享的数据服务代码  

在 WeatherApp 项目中，可以编写跨所有平台共享的 .NET Standard 库代码。 此库自动包含在 iOS、Android 和 Windows 项目生成的应用包中。  
  
要运行此示例，必须先在 [http://openweathermap.org/appid](http://openweathermap.org/appid) 注册免费 API 密钥。  
  
然后，执行以下步骤，将代码添加到 .NET Standard 库，以访问和存储天气服务中的数据：  
  
1.  右键单击“WeatherApp”项目，然后选择“添加”>“类…”。在“添加新项”  对话框中，将文件命名为 **Weather.cs**。 将使用此类来存储天气数据服务的数据。  
  
2.  将 **Weather.cs** 的全部内容替换为以下内容：  
  
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
  
3.  将另一个类“DataService.cs”添加到 WeatherApp 项目中，用于处理天气数据服务中的 JSON 数据。  
  
4.  将 **DataService.cs** 的全部内容替换为以下代码：  
  
    ```csharp  
    using System.Net.Http;  
    using System.Threading.Tasks;  
    using Newtonsoft.Json;  
    
    namespace WeatherApp  
    {  
        public class DataService  
        {  
            public static async Task<dynamic> getDataFromService(string queryString)  
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
  
5.  将第三个类“Core”添加到 WeatherApp 项目中，用于放置共享业务逻辑。 此代码形成包含邮政编码的查询字符串，调用天气数据服务，并填充 Weather 类实例。  
  
6.  将 **Core.cs** 的内容替换为以下内容：  
  
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
                string key = "YOUR KEY HERE";  
                string queryString = "http://api.openweathermap.org/data/2.5/weather?zip="  
                    + zipCode + ",us&appid=" + key + "&units=imperial";  
  
                dynamic results = await DataService.getDataFromService(queryString).ConfigureAwait(false);  
  
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
  
7.  生成 WeatherApp 库项目，以确保代码正确无误。  
  
##  <a name="uicode"></a> 开始编写共享的 UI 代码  

使用 Xamarin.Forms，可以在 .NET Standard 库中实现共享 UI 代码。 按照下面这些步骤操作可以向项目添加带按钮的页面，此按钮使用上一部分中添加的天气数据服务代码返回的数据来更新自己的文本：  
  
1.  右键单击“WeatherApp”项目，并依次选择“添加”>“新项…”，添加名为“WeatherPage.cs”的内容页。在“添加新项”对话框中，选择“内容页”。 请勿选择“内容页 (C#)”或“内容视图”。 将它命名为“WeatherPage.cs”。  
  
     ![添加新的 Xamarin.Forms XAML 页面](../cross-platform/media/crossplat-xamarin-formsguide-6.png "CrossPlat Xamarin FormsGuide 6")  
  
     Xamarin.Forms 基于 XAML，因此，此步骤创建 **WeatherPage.xaml** 文件和嵌套的代码隐藏文件 **WeatherPage.xaml.cs**。 这使你可以通过 XAML 或代码生成 UI。 在此演练中，将通过这两种方式执行一些操作。  
  
2.  若要向“WeatherPage”屏幕添加按钮，请将“WeatherPage.xaml”的内容替换为以下内容：  
  
    ```xaml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <ContentPage xmlns="http://xamarin.com/schemas/2014/forms"  
           xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"  
           x:Class="WeatherApp.WeatherPage"
           Title="Sample Weather App">  
      <Button x:Name="getWeatherBtn" 
              Text="Get Weather"
              Clicked="GetWeatherBtn_Clicked" />  
    </ContentPage>  
    ```  
  
     请注意，必须使用 **X:name** 特性定义按钮名称，以便可以从代码隐藏文件内部通过名称引用此按钮。  
  
3.  若要为按钮的已单击事件添加事件处理程序以更新按钮文本，请用以下代码替换 WeatherPage.xaml.cs 的内容。 （可随意将“60601”更改为其他邮政编码。）  
  
    ```csharp  
    using System;  
    using Xamarin.Forms;  
  
    namespace WeatherApp  
    {  
        public partial class WeatherPage: ContentPage  
        {  
            public WeatherPage()  
            {  
                InitializeComponent();  
  
                //Set the default binding to a default object for now  
                BindingContext = new Weather();  
            }  
  
            private async void GetWeatherBtn_Clicked(object sender, EventArgs e)  
            {  
                Weather weather = await Core.GetWeather("60601");  
                getWeatherBtn.Text = weather.Title;  
            }  
        }  
    }  
    ```  
  
4.  若要在应用启动时将 **WeatherPage** 作为第一个屏幕打开，请将 **App.cs** 中的默认构造函数替换为以下代码：  
  
    ```csharp  
    public App()  
    {
        InitializeComponent();

        MainPage = new NavigationPage(new WeatherPage());  
    }  
    ```  
  
5.  生成 WeatherApp 项目，以确保代码正确无误。  
  
##  <a name="test"></a> 使用适用于 Android 的 Visual Studio 仿真程序测试你的应用。  

现在即可运行应用！ 现在仅运行 Android 版本，验证该应用是否从天气服务获取数据。 稍后，在添加更多 UI 元素后，还将运行 iOS 和 UWP 版本。   
  
1.  右键单击“WeatherApp.Android”项目，并选择“设为启动项目”，将它设为启动项目。  
  
2.  在 Visual Studio 工具栏中，“WeatherApp.Android”被列为目标项目。 选择一个 Android 仿真程序以进行调试，并点击“F5” 。 建议使用“VisualStudio”仿真器选项之一，用于在适用于 Android 的 Visual Studio 仿真器中运行应用。  
  
     ![选择 Android Emulator 调试目标](../cross-platform/media/crossplat-xamarin-formsguide-7.png "CrossPlat Xamarin FormsGuide 7")  
  
3.  当应用在仿真程序中启动时，单击“获取天气信息”  按钮。 应看到按钮文本更新为“芝加哥”，这是从天气服务检索到的数据的 Title 属性。  
  
     ![点击按钮前和点击后显示的天气应用](../cross-platform/media/crossplat-xamarin-formsguide-8.png "CrossPlat Xamarin FormsGuide 8")  
  
##  <a name="finish"></a>跨平台完成具有本机外观的 UI  

Xamarin.Forms 会呈现每个平台的本机 UI 控件，以便你的应用会自动拥有本机外观。 若要更清晰地查看这一内容，可通过邮政编码的输入字段来完成 UI，然后显示从服务返回的天气数据。  
  
1.  将 **WeatherPage.xaml** 的内容替换为以下代码。 使用之前介绍的 X:name 属性命名的元素可以通过代码引用。 Xamarin.Forms 还提供了许多[布局选项](http://developer.xamarin.com/guides/xamarin-forms/controls/layouts/) (xamarin.com)。 在本文中，WeatherPage 使用 [Grid](http://developer.xamarin.com/api/type/Xamarin.Forms.Grid/) (xamarin.com) 和 [StackLayout](http://developer.xamarin.com/api/type/Xamarin.Forms.StackLayout/) (xamarin.com)。  
  
    ```xaml  
    <?xml version="1.0" encoding="utf-8" ?>
    <ContentPage xmlns="http://xamarin.com/schemas/2014/forms"  
                 xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"  
                 x:Class="WeatherApp.WeatherPage"
                 Title="Sample Weather App">

        <ContentPage.Resources>
            <ResourceDictionary>
                <Style x:Key="labelStyle" TargetType="Label">
                    <Setter Property="FontSize" Value="Small" />
                    <Setter Property="TextColor" Value="#404040" />
                </Style>
                <Style x:Key="fieldStyle" TargetType="Label">
                    <Setter Property="FontSize" Value="Medium" />
                    <Setter Property="Margin" Value="10,0,0,0" />
                </Style>
            </ResourceDictionary>
        </ContentPage.Resources>

        <StackLayout>
            <Grid BackgroundColor="#545454" Padding="10, 10, 10, 10">
                <Grid.RowDefinitions>
                    <RowDefinition Height="Auto" />
                    <RowDefinition Height="Auto" />
                </Grid.RowDefinitions>

                <Grid.ColumnDefinitions>
                    <ColumnDefinition Width="Auto" />
                    <ColumnDefinition Width="*" />
                    <ColumnDefinition Width="Auto" />
                </Grid.ColumnDefinitions>
            
                <Label Text="Search by Zip Code" 
                       Grid.Row="0" Grid.Column="0" Grid.ColumnSpan="3"
                       HorizontalOptions="Center"
                       TextColor="White" FontAttributes="Bold" FontSize="Medium" />
            
                <Label x:Name="zipCodeLabel" Text="Zip Code:" 
                       Grid.Row="1" Grid.Column="0"
                       VerticalOptions="Center"
                       Style="{StaticResource labelStyle}"
                       TextColor="#C0C0C0" />
            
                <Entry x:Name="zipCodeEntry"
                       Grid.Row="1" Grid.Column="1"
                       VerticalOptions="Center"
                       Margin="5,0"
                       BackgroundColor="DarkGray"
                       TextColor="White" />
            
                <Button x:Name="getWeatherBtn" Text="Get Weather" 
                        Grid.Row="1" Grid.Column="2"
                        HorizontalOptions="Center"
                        VerticalOptions="Center"
                        BorderWidth="1"
                        BorderColor="White"
                        BackgroundColor="DarkGray"
                        TextColor="White"
                        Clicked="GetWeatherBtn_Clicked" />
            </Grid>

            <ScrollView VerticalOptions="FillAndExpand">
                <StackLayout Padding="10,10,10,10" HorizontalOptions="Start">
                    <Label Text="Location" Style="{StaticResource labelStyle}" />
                    <Label Text="{Binding Title}" Style="{StaticResource fieldStyle}" />
                
                    <Label Text="Temperature" Style="{StaticResource labelStyle}" />
                    <Label Text="{Binding Temperature}" Style="{StaticResource fieldStyle}" />
                
                    <Label Text="Wind Speed" Style="{StaticResource labelStyle}" />
                    <Label Text="{Binding Wind}" Style="{StaticResource fieldStyle}" />
                
                    <Label Text="Humidity" Style="{StaticResource labelStyle}" />
                    <Label Text="{Binding Humidity}" Style="{StaticResource fieldStyle}" />
                
                    <Label Text="Visibility" Style="{StaticResource labelStyle}" />
                    <Label Text="{Binding Visibility}" Style="{StaticResource fieldStyle}" />
                
                    <Label Text="Time of Sunrise" Style="{StaticResource labelStyle}" />
                    <Label Text="{Binding Sunrise}" Style="{StaticResource fieldStyle}" />
                
                    <Label Text="Time of Sunset" Style="{StaticResource labelStyle}" />
                    <Label Text="{Binding Sunset}" Style="{StaticResource fieldStyle}" />
                </StackLayout>
            </ScrollView>
        </StackLayout>
    </ContentPage>  
     ```  
  
     虽然本文未说明，但可以使用 OnPlatform 标记，选择当前运行应用的平台的专用属性值（请参阅[基本 XAML 语法](http://developer.xamarin.com/guides/xamarin-forms/user-interface/xaml-basics/essential_xaml_syntax/) (xamarin.com)）。 在代码隐藏文件中，你可以将 [Device.OnPlatform API](http://developer.xamarin.com/guides/xamarin-forms/platform-features/device/) 用于同一目的。  
  
2.  在 **WeatherPage.xaml.cs**中，将 **GetWeatherBtn_Clicked** 事件处理程序替换为以下代码。 此代码验证输入字段中是否有邮政编码，检索相应邮政编码的数据，将整个页面的绑定上下文设置为生成的 Weather 实例，再将按钮文本设置为“重新搜索”。 请注意，由于 UI 中的每个标签都绑定到 Weather 类属性，因此如果将屏幕的绑定上下文设置为 Weather 实例，这些标签会自动更新。  
  
    ```csharp  
    private async void GetWeatherBtn_Clicked(object sender, EventArgs e)  
    {  
        if (!String.IsNullOrEmpty(zipCodeEntry.Text))  
        {  
            Weather weather = await Core.GetWeather(zipCodeEntry.Text);  
            BindingContext = weather;  
            getWeatherBtn.Text = "Search Again";  
        }  
    }  
    ```  
  
3.  右键单击相应项目，选择“设为启动项目”，并在设备或仿真器/模拟器中启动应用，从而在所有三个平台（Android、iOS 和 Windows）上运行应用。 输入有效的美国五位数邮政编码，并按“获取天气信息”按钮，以显示相应区域的天气数据（如下所示）。 需要将 Visual Studio 连接到 iOS 项目网络上的 Mac OS X 计算机。  
  
     ![Android、iOS 和 Windows Phone 上的天气应用示例](../cross-platform/media/crossplat-xamarin-formsguide-1.png "CrossPlat Xamarin FormsGuide 1")  
  
此项目完整的源代码位于 [xamarin-forms-samples repository on GitHub](https://github.com/xamarin/xamarin-forms-samples/tree/master/Weather)（GitHub 上的 xamarin-forms-samples 存储库）中。