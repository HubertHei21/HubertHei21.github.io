---
title: ASP.NET CORE WebApi中使用EF Core DB First
author: Hubert
date: 2023-03-03
category: .NET
layout: post
---

### 1.NugetPackage

#### 1.1 SQL Server

* Package

~~~C#
Install-Package Microsoft.EntityFrameworkCore
Install-Package Microsoft.EntityFrameworkCore.SqlServer
Install-Package Microsoft.EntityFrameworkCore.Tools



Install-Package Microsoft.VisualStudio.Web.CodeGeneration.Design

Scaffold-DbContext "Server=127.0.0.1;Database=hisdata;User Id=sa;Password=000626;TrustServerCertificate=true" Microsoft.EntityFrameworkCore.SqlServer -O Entity -F
~~~

* 
* 
* 
* 
