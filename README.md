<h1>Steps taken to add google authentication</h1>

<h2>Google</h2>
<ol>
  <li>Navigate to Google cloud console.</li>
  <li>Create new project.</li>
  <li>Click on OAuth consent screen.</li>
  <li>Go through process of OAuth consent screen.</li>
  <li>Now click on Credentials.</li>
  <li>Click on "Create Credentials" -> "Create OAuth client ID" -> obtain Client ID and Client Secret.</li>
</ol>

<h2>Visual studio</h2>
<ol>
  <li>In side visual studio, open Package Manager Console and input the following line to download Google Authentication middleware Nuget package</li>
  ```NuGet\Install-Package Microsoft.AspNetCore.Authentication.Google -Version 7.0.9```
</ol>

