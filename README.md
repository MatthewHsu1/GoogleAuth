<h1>Steps taken to add google authentication</h1>

<h2>Google</h2>
<ol>
  <li>Navigate to Google cloud console.</li>
  <li>Create new project.</li>
  <img src="https://github.com/MatthewHsu1/GoogleAuth/blob/master/Screenshot%202024-05-14%20070656.png" width="50%" height="50%" />
  <li>Click on OAuth consent screen.</li>
  <img src="https://github.com/MatthewHsu1/GoogleAuth/blob/master/Screenshot%202024-05-14%20073030.png" width="50%" height="50%" />
  <li>Go through process of OAuth consent screen.</li>
  <li>Now click on Credentials.</li>
  <img src="https://github.com/MatthewHsu1/GoogleAuth/blob/master/Screenshot%202024-05-14%20073058.png" width="50%" height="50%" />
  <li>Click on "Create Credentials" -> "Create OAuth client ID" -> obtain Client ID and Client Secret.</li>
  <img src="https://github.com/MatthewHsu1/GoogleAuth/blob/master/Screenshot%202024-05-14%20073114.png" width="50%" height="50%" /> 
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

```
{  "Authentication:Google:ClientId": "your Google client ID",
   "Authentication:Google:ClientSecret": "your Google client secret"}
```

<ol start='3'>
  <li>Open the Program.cs file and add the following code under the builder.Service.AddAuthentication method.</li>
</ol>

```
.AddGoogle(googleOptions =>
{
    googleOptions.ClientId = builder.Configuration["Authentication:Google:ClientId"];
    googleOptions.ClientSecret = builder.Configuration["Authentication:Google:ClientSecret"];
})
```

<h1>Connecting to a local SQL Database</h1>

<ol>
  <li>Update the \GoogleAuth\Data\ApplicationDbContext.cs file to include ASP.NET Core Identity and IdentityServer integration</li>
  <li>Install necessary Nuget packages</li>
</ol>

```
dotnet add package Duende.IdentityServer
dotnet add package Microsoft.AspNetCore.ApiAuthorization.IdentityServer
```

<ol>
   <li> Configure your appsetting.json to have a connection to your database. ie. </li>
</ol>

```
{
  "ConnectionStrings": {
     "DefaultConnection": "Server=LAPTOP-BIAV7Q4D; Database=google_auth_db; Trusted_Connection=True; Encrypt=false;"
  },
  "Logging": {
    "LogLevel": {
      "Default": "Information",
      "Microsoft.AspNetCore": "Warning"
    }
  },
  "IdentityServer": {
    "Clients": {
      "GoogleAuth.Client": {
        "Profile": "IdentityServerSPA"
      }
    }
  },
  "AllowedHosts": "*"
}
```
<ol>
   <li> Installed the following Nuget package. </li>
</ol>

```
dotnet tool install --global dotnet-ef
```

<ol>
   <li>Change directory into your project, in my case, it is</li>
</ol>

```
cd GoogleAuth
```

<ol>
  <li>Execcute our dotnet ef command</li>
</ol>

```
dotnet ef database update
```

