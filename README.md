<h1>Steps taken to add google authentication</h1>

<ol>
  <ol>
    <li>Navigate to Google cloud console</li>
    <li>Create new project</li>
    <li>Click on OAuth consent screen</li>
    <li>Go through set of OAuth consent screen</li>
    <li>Now click on Credentials</li>
    <li>Click on "Create Credentials" -> "Create OAuth client ID" -> obtain Client ID and Client Secret</li>
  </ol>
  <ol>
    <li>In side visual studio, open Package Manager Console and input the following line to download Google Authentication middleware Nuget package</li>
    `NuGet\Install-Package Microsoft.AspNetCore.Authentication.Google -Version 7.0.9`
  </ol>
</ol>
