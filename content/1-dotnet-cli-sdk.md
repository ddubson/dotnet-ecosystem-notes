---
title: "1 - Get the .NET SDK and CLI!"
date: 2019-06-20T17:51:13-04:00
anchor: "dotnet-cli"
weight:
---

Here's where you start.

## .NET Core SDK and CLI

The first step is to download and install the `.NET Core SDK`. This is the development kit for .NET that will be the engine for your application.

If you're familiar with Java, `.NET Core SDK` is similar to `Oracle JDK`, `OpenJDK`, or other JDK variants.

### On MacOS

The easiest way to obtain the SDK is to use [Homebrew](https://brew.sh)

In a terminal, run...

{{<highlight bash>}}
brew install dotnet-sdk
{{</highlight>}}

The `.NET SDK` contains within it the `.NET CLI` that we'll use going forward.

To make sure it successfully installed and accessible, run...

{{<highlight bash>}}
dotnet --version
{{</highlight>}}

You should receive an answer with a version number, such as `2.2.107` or later.

