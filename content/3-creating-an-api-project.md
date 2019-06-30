---
title: "Creating a REST API with .NET Core"
date: 2019-06-23T19:54:54-04:00
anchor: "creating-an-api-with-dotnet-core"
weight: 52
---

Let's build a REST API. 

As an example, we'll build a weather service that will give us some real interesting facts about current weather conditions in the world.

.NET Core CLI has a concept of **templates** which we'll be using to generate projects within a solution.

{{<highlight bash>}}
# Create a directory and navigate to it
mkdir dotnet-weather-station
cd dotnet-weather-station

# Make this directory our 'solution' with the name WeatherStation
dotnet new sln --name WeatherStation

# Let's take a look at the selection of templates .NET Core provides
dotnet new --list

# The closest option for our use case is the webapi option (shorthand)
# Create an API project using the webapi template
dotnet new webapi --output src/WeatherStation.API --name WeatherStation.API

# Clean up unnecessary auto-generated controllers
rm -rf src/WeatherStation.API/Controllers

# Create an accompanying test project using xUnit which will hold all the API test cases
dotnet new xunit --output tests/WeatherStation.API.Tests --name WeatherStation.API.Tests

# Clean up unnecessary auto-generated test cases
rm tests/WeatherStation.API.Tests/UnitTest1.cs

# Add the WeatherStation.API project reference to the test project
dotnet add tests/WeatherStation.API.Tests reference src/WeatherStation.API/WeatherStation.API.csproj

# Add the newly created API project and test API project to be part of the 'solution'
dotnet sln WeatherStation.sln add src/WeatherStation.API/WeatherStation.API.csproj
dotnet sln WeatherStation.sln add src/WeatherStation.API.Tests/WeatherStation.API.Tests.csproj
{{</highlight>}}

At this point, we can import the project into JetBrains Rider IDE by opening a solution that we have just
created.

The structure of our directory tree should look similar to below. Let's take this opportunity to 
describe what solution (.sln) and project (.csproj) do.

![Directory structure - New solution](/images/directory-structure-new-solution.svg)

It's important to note that all the projects in the `tests` directory are never packaged as part of the runtime executable.



