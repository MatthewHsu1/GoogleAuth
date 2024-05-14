<h1>Steps taken to add google authentication</h1>

<h2>Google</h2>
 ![Alt text](/Screenshot 2024-05-14 070656.png)
<ol>
  <li>Navigate to Google cloud console.</li>
  <li>Create new project.</li>
  <img src="https://github.com/MatthewHsu1/GoogleAuth/blob/master/Screenshot%202024-05-14%20070656.png" width="50%" height="50%" />
  <li>Click on OAuth consent screen.</li>
  <li>Go through process of OAuth consent screen.</li>
  <li>Now click on Credentials.</li>
  <li>Click on "Create Credentials" -> "Create OAuth client ID" -> obtain Client ID and Client Secret.</li>
</ol>

<h2>Visual studio</h2>
<ol>
  <li>In side visual studio, open Package Manager Console and input the following line to download Google Authentication middleware Nuget package</li>
</ol>

```
  NuGet\Install-Package Microsoft.AspNetCore.Authentication.Google -Version 7.0.9
```

<ol start="2">
  <li>Right-click the project, select Manage User Secrets, and type the following code.</li>
</ol>

```{  "Authentication:Google:ClientId": "your Google client ID",
   "Authentication:Google:ClientSecret": "your Google client secret"}
```

<ol start='3'>
  <li>Open the Program.cs file and add the following code under the builder.Service.AddAuthentication method.</li>
</ol>

```.AddGoogle(googleOptions =>
{
    googleOptions.ClientId = builder.Configuration["Authentication:Google:ClientId"];
    googleOptions.ClientSecret = builder.Configuration["Authentication:Google:ClientSecret"];
})
```

