---
title: .NET Framework WebApi 下载文件
author: Hubert
date: 2023-02-15
category: .NET
layout: post
---

##### .NET Framework ASP.NET Web API

* Download File

~~~ C#
/// <summary>
/// 文件下载
/// </summary>
/// <returns></returns>
[HttpGet]
public HttpResponseMessage Download()
{
    // 获取根路径下zip文件
    var basePath = AppDomain.CurrentDomain.BaseDirectory;
    var dictionary = new DirectoryInfo(basePath);
    var file = dictionary.GetFiles().FirstOrDefault(p => p.Extension.ToLower().Contains("zip"));
    if (file?.DirectoryName == null)
    {
        return Request.CreateResponse(HttpStatusCode.OK, ErrorEnum.NotFindData);
    }
    var response = new HttpResponseMessage(HttpStatusCode.OK);
    response.Content = new StreamContent(file.OpenRead());
    response.Content.Headers.ContentDisposition = new ContentDispositionHeaderValue("attachment")
    {
        FileName = file.Name
    };
    //.zip MIME Type "application/zip"
    //https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/MIME_types/Common_types
    response.Content.Headers.ContentType = new MediaTypeHeaderValue("application/zip");
    return response;
}
~~~

* Zip File

Nuget Package: [DotNetZip](https://www.nuget.org/packages/DotNetZip/)

~~~ C#
//从 zip 存档中压缩文件：  
using (var zipFile =  new  ZipFile())  
{  
   // 空字符串参数确保文件被归档到存档的根目录  
   zipFile.AddFile(@"C:\Test\Data.txt",  string .Empty);  
   zipFile.Save(@"C:\Test\Data.zip");  
}  
//从 zip 存档中解压文件：  
using (var zipFile =  new  ZipFile(@"C:\Test\Data.zip"))  
{  
   zipFile.ExtractAll(@"C:\Test\Output");  
} 
~~~
