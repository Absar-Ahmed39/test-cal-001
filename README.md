# Getting started

Google API for searching youtube videos

## How to Build

The generated code uses the Newtonsoft Json.NET NuGet Package. If the automatic NuGet package restore
is enabled, these dependencies will be installed automatically. Therefore,
you will need internet access for build.

"This library requires Visual Studio 2017 for compilation."
1. Open the solution (YoutubeSearchAPI.sln) file.
2. Invoke the build process using `Ctrl+Shift+B` shortcut key or using the `Build` menu as shown below.

![Building SDK using Visual Studio](https://apidocs.io/illustration/cs?step=buildSDK&workspaceFolder=Youtube%20Search%20API-CSharp&workspaceName=YoutubeSearchAPI&projectName=YoutubeSearchAPI.Tests)

## How to Use

The build process generates a portable class library, which can be used like a normal class library. The generated library is compatible with Windows Forms, Windows RT, Windows Phone 8,
Silverlight 5, Xamarin iOS, Xamarin Android and Mono. More information on how to use can be found at the [MSDN Portable Class Libraries documentation](http://msdn.microsoft.com/en-us/library/vstudio/gg597391%28v=vs.100%29.aspx).

The following section explains how to use the YoutubeSearchAPI library in a new console project.

### 1. Starting a new project

For starting a new project, right click on the current solution from the *solution explorer* and choose  ``` Add -> New Project ```.

![Add a new project in the existing solution using Visual Studio](https://apidocs.io/illustration/cs?step=addProject&workspaceFolder=Youtube%20Search%20API-CSharp&workspaceName=YoutubeSearchAPI&projectName=YoutubeSearchAPI.Tests)

Next, choose "Console Application", provide a ``` TestConsoleProject ``` as the project name and click ``` OK ```.

![Create a new console project using Visual Studio](https://apidocs.io/illustration/cs?step=createProject&workspaceFolder=Youtube%20Search%20API-CSharp&workspaceName=YoutubeSearchAPI&projectName=YoutubeSearchAPI.Tests)

### 2. Set as startup project

The new console project is the entry point for the eventual execution. This requires us to set the ``` TestConsoleProject ``` as the start-up project. To do this, right-click on the  ``` TestConsoleProject ``` and choose  ``` Set as StartUp Project ``` form the context menu.

![Set the new cosole project as the start up project](https://apidocs.io/illustration/cs?step=setStartup&workspaceFolder=Youtube%20Search%20API-CSharp&workspaceName=YoutubeSearchAPI&projectName=YoutubeSearchAPI.Tests)

### 3. Add reference of the library project

In order to use the YoutubeSearchAPI library in the new project, first we must add a projet reference to the ``` TestConsoleProject ```. First, right click on the ``` References ``` node in the *solution explorer* and click ``` Add Reference... ```.

![Open references of the TestConsoleProject](https://apidocs.io/illustration/cs?step=addReference&workspaceFolder=Youtube%20Search%20API-CSharp&workspaceName=YoutubeSearchAPI&projectName=YoutubeSearchAPI.Tests)

Next, a window will be displayed where we must set the ``` checkbox ``` on ``` YoutubeSearchAPI.Tests ``` and click ``` OK ```. By doing this, we have added a reference of the ```YoutubeSearchAPI.Tests``` project into the new ``` TestConsoleProject ```.

![Add a reference to the TestConsoleProject](https://apidocs.io/illustration/cs?step=createReference&workspaceFolder=Youtube%20Search%20API-CSharp&workspaceName=YoutubeSearchAPI&projectName=YoutubeSearchAPI.Tests)

### 4. Write sample code

Once the ``` TestConsoleProject ``` is created, a file named ``` Program.cs ``` will be visible in the *solution explorer* with an empty ``` Main ``` method. This is the entry point for the execution of the entire solution.
Here, you can add code to initialize the client library and acquire the instance of a *Controller* class. Sample code to initialize the client library and using controller methods is given in the subsequent sections.

![Add a reference to the TestConsoleProject](https://apidocs.io/illustration/cs?step=addCode&workspaceFolder=Youtube%20Search%20API-CSharp&workspaceName=YoutubeSearchAPI&projectName=YoutubeSearchAPI.Tests)

## How to Test

The generated SDK also contain one or more Tests, which are contained in the Tests project.
In order to invoke these test cases, you will need *NUnit 3.0 Test Adapter Extension for Visual Studio*.
Once the SDK is complied, the test cases should appear in the Test Explorer window.
Here, you can click *Run All* to execute these test cases.

## Initialization

### Authentication
In order to setup authentication and initialization of the API client, you need the following information.

| Parameter | Description |
|-----------|-------------|
| key | API Key |



API client can be initialized as following.

```csharp
// Configuration parameters and credentials
string key = "AIzaSyDUvW2Jbb0ob8a2tDidm8RQzYxczT2OroA"; // API Key

YoutubeSearchAPIClient client = new YoutubeSearchAPIClient(key);
```



# Class Reference

## <a name="list_of_controllers"></a>List of Controllers

* [APIController](#api_controller)

## <a name="api_controller"></a>![Class: ](https://apidocs.io/img/class.png "YoutubeSearchAPI.Tests.Controllers.APIController") APIController

### Get singleton instance

The singleton instance of the ``` APIController ``` class can be accessed from the API Client.

```csharp
APIController client = client.Client;
```

### <a name="search_endpoint"></a>![Method: ](https://apidocs.io/img/method.png "YoutubeSearchAPI.Tests.Controllers.APIController.SearchEndpoint") SearchEndpoint

> TODO: Add a method description


```csharp
Task<Standard.Models.YoutubeJSONMasterObject> SearchEndpoint(Standard.Models.PartEnum part, string q, string type = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| part |  ``` Required ```  ``` DefaultValue ```  | The part parameter specifies a comma-separated list of one or more search resource properties that the API response will include. Set the parameter value to snippet. |
| q |  ``` Required ```  | The q parameter specifies the query term to search for. |
| type |  ``` Optional ```  | The type parameter restricts a search query to only retrieve a particular type of resource. |


#### Example Usage

```csharp
var part = Standard.Models.PartEnumHelper.ParseString("snippet");
string q = "every youtube video ever";
string type = "video";

Standard.Models.YoutubeJSONMasterObject result = await client.SearchEndpoint(part, q, type);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 400 | Custom 400 Error message occurred |
| 401 | Custom 401 Error Message Occurred |


[Back to List of Controllers](#list_of_controllers)



