# Getting Started with Xamarin Cards

This demo sample explains about how to use the cards control in Xamarin.Forms

This section explains you the steps required to add content to SfCardView with indicator and add SfCardView to SCardLayout. This section covers only the minimal features needed to get started with the cards.

You can add cards reference using one of the following methods:

**Method 1: Adding cards reference from nuget.org**

Syncfusion Xamarin components are available in nuget.org. To add cards to your project, open the NuGet package manager in Visual Studio, search for Syncfusion.Xamarin.Cards, and then install it.

Adding Xamarin.Forms Cards reference

![Getting Started](getting-started_image/img3.png)

Note : Install the same version of the cards NuGet in all the projects.

**Method 2: Adding cards reference from toolbox**

Syncfusion provides Xamarin Toolbox. Using this toolbox, you can drag the SfCardView and SfCardLayout to the XAML page. It will automatically install the required NuGet packages and add the namespace to the page. To install Syncfusion Xamarin Toolbox, refer to Toolbox.

**Method 3: Adding Cards assemblies manually from the installed location**

If you prefer to manually reference the assemblies instead of referencing from NuGet, add the following assemblies in respective projects.

Location : {Installed location}/{version}/Xamarin/lib

**PCL**

Syncfusion.Cards.XForms.dll
Syncfusion.Core.XForms.dll
Syncfusion.Licensing.dll

**Android**

Syncfusion.Cards.XForms.Android.dll
Syncfusion.Cards.XForms.dll
Syncfusion.Core.XForms.dll
Syncfusion.Core.XForms.Android.dll
Syncfusion.Licensing.dll

**iOS**

Syncfusion.Cards.XForms.iOS.dll
Syncfusion.Cards.XForms.dll
Syncfusion.Core.XForms.dll
Syncfusion.Core.XForms.iOS.dll
Syncfusion.Licensing.dll

**UWP**	

Syncfusion.Cards.XForms.UWP.dll
Syncfusion.Cards.XForms.dll
Syncfusion.Core.XForms.dll
Syncfusion.Core.XForms.UWP.dll
Syncfusion.Licensing.dll

NOTE : To know more about obtaining our components, refer to these links for Mac and Windows.

**IMPORTANT**

Starting with v16.2.0.x, if you reference Syncfusion assemblies from the trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to Syncfusion license key to know about registering Syncfusion license key in your Xamarin application to use our components.

Launching the application on each platform with cards
To use the cards inside an application, each platform application requires some additional configurations. The configurations vary from platform to platform and are discussed in the following sections:

NOTE : If you are adding the references from toolbox, below steps are not needed.

**iOS**

To launch the cards in iOS, call the SfCardViewRenderer.Init() method in the FinishedLaunching overridden method of the AppDelegate class after the Xamarin.Forms framework has been initialized and before the LoadApplication method is called as demonstrated in the following code sample:
```
public override bool FinishedLaunching(UIApplication app, NSDictionary options) 
{ 
	… 
	global::Xamarin.Forms.Forms.Init();
	Syncfusion.XForms.iOS.Cards.SfCardViewRenderer.Init();
	LoadApplication(new App()); 
	…
}
```
**Universal Windows Platform (UWP)**

To deploy the cards in Release mode, you need to initialize the cards assemblies in App.xaml.cs in the UWP project as shown in the below code snippets.
```
// In App.xaml.cs 
protected override void OnLaunched(LaunchActivatedEventArgs e)
{ 
	… 
	if (rootFrame == null) 
	{ 
		List<Assembly> assembliesToInclude = new List<Assembly>();
		assembliesToInclude.Add(typeof(Syncfusion.XForms.UWP.Cards.SfCardViewRenderer).GetTypeInfo().Assembly);
		Xamarin.Forms.Forms.Init(e, assembliesToInclude);
	} 
    … 
}
```
**Android**

The Android platform does not require any additional configuration to render the cards.

## Initialize cards

Import the Cards namespace as shown in the following code in your respective page.

```
xmlns:cards="clr-namespace:Syncfusion.XForms.Cards;assembly=Syncfusion.Cards.XForms"
SfCardView
```

Initialize a card view with Content as shown in the following code.

**[XAML]**

```
<cards:SfCardView>

	<Label Text="SfCardView"/>

</cards:SfCardView>

```
Run the project and check if you get following output to make sure that you have configured your project properly to add Cards.

## Initializing Xamarin.Forms SfCardView

**SwipeToDismiss**

The SwipeToDismiss property is used to enable or disable swiping in SfCardView.

**[XAML]**
```
<cards:SfCardView SwipeToDismiss="true">
	<Label Text="SfCardView"/>
</cards:SfCardView>
```
NOTE : This property won’t work when adding the SfCardView as a child of SfCardLayout.

## SwipeToDismiss in Xamarin.Forms SfCardView

**Dismiss the card programmatically**

We can get a view state of the card using the IsDismissed property, which also allows the user to programmatically alter the view state of the card.

**[XAML]**
```
<cards:SfCardView IsDismissed="true">
     <Label Text="SfCardView"/>
</cards:SfCardView>
```
NOTE : This property won’t work when adding the SfCardView as a child of SfCardLayout.

### SfCardLayout

Initialize a card layout with card view as shown in the following code.

**[XAML]**
```
<cards:SfCardLayout SwipeDirection="Left" HeightRequest="500" BackgroundColor="#F0F0F0">

	<cards:SfCardView>
		<Label  Text="Cyan" BackgroundColor="Cyan"/>
	</cards:SfCardView>

	<cards:SfCardView>
		<Label  Text="Yellow" BackgroundColor="Yellow"/>
	</cards:SfCardView>

	<cards:SfCardView>
		<Label  Text="Orange" BackgroundColor="Orange"/>
	</cards:SfCardView>  

</cards:SfCardLayout>
```
![](getting-started_images/layout)
