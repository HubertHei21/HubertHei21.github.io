---
title: .NET Framework WebApi Q&A
author: Hubert
date: 2023-02-15
category: .NET
layout: post
---

##### .NET Framework ASP.NET Web API

* Api DEMO

  ~~~ C#
  /// <summary>
  /// DEMO
  /// </summary>
  /// <returns></returns>
  [HttpGet]
  public HttpResponseMessage Test()
  {
      return Request.CreateResponse(HttpStatusCode.OK, "Success");
  }
  ~~~

* MIME Type

  > .zip => "application/zip" \
  > [LINK](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/MIME_types/Common_types)

* .NET 4.0 Async Await

> NuGet Package: Microsoft.Bcl.Async
