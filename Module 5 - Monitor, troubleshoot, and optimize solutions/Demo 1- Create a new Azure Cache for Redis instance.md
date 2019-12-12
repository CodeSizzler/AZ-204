<h1>Create a new Azure Cache for Redis instance</h1>

<h2>Introduction</h2>
<p>In this article, you will learn to incorporate Azure Cache for Redis into a .NET Framework app to have access to a secure, dedicated cache that is accessible from any application within Azure.</p>

<h2>Prerequisites</h2>
<p>To perform this demo, you must need a valid Azure Subscription and some knowledge on Azure Cache and Visual Studio 2019.</p>

<h2>Steps:</h2>
<p>1. Log-in to Azure portal with your account using www.portal.azure.com. Select Create a Resource in the Azure portal.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-001/1.png"/>
<p>2. Now select Azure Cache for Redis in the Database category. Now create the Azure Cache with the following configuration as shown in the below picture.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-001/2.png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-001/2.1.png"/>
<p>3. Once your deployment is completed, navigate to the resource and then copy the primary key in the Access keys.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-001/3.png"/>
<p>4. Now copy the host name in the properties section</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-001/4.png"/>
<p>Create a file on your computer named CacheSecrets.config and place it in a location where it won't be checked in with the source code of your sample application. In this demo CacheSecrets.config file is located here, C:\AppSecrets\CacheSecrets.config.</p>
<p>Now edit the CacheSecrets.config and add the script  from - http://bit.ly/RedishScript.</p>

<h2>Create a console app</h2>
<p>In Visual Studio, click File > New > Project.</p>
<p>Under Visual C#, click Windows Classic Desktop and then click Console App, and OK to create a new console application.</p>
<p>Once you created the console app, now configure the app in the visual studio.</p>
<p>In Visual Studio, click Tools > NuGet Package Manager > Package Manager Console, and run the following command from the Package Manager Console window</p>
<p>Install-Package StackExchange.Redis</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-001/5.png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-001/5.1.png"/>
<p>Once the command run successfully you will the following result.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-001/6.png"/>
<p>Now connect the app to the cache, In Visual Studio, open your App.config file and update the command in the following link to include an appSettings file attribute that references the CacheSecrets.config file.</p>
<p>http://bit.ly/CacheScript</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-001/7.png"/>
<p>In Solution Explorer, right-click References and click Add a reference. Add a reference to the System.Configuration assembly.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-001/8.png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-001/8.1.png"/>
<p>Add the following using command in the program.cs.</p>
            <p>using StackExchange.Redis;</p>
            <p>using System.Configuration;</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-001/9.png"/>
<p>The connection to the Azure Cache for Redis is managed by the ConnectionMultiplexer class. This class should be shared and reused throughout your client application. Do not create a new connection for each operation. In Program.cs, add the following members to the Program class of your console application.</p>
<p>private static Lazy<ConnectionMultiplexer> lazyConnection = new Lazy<ConnectionMultiplexer>(() =></p>
    <p>{</p>
        <p>string cacheConnection = ConfigurationManager.AppSettings["CacheConnection"].ToString();</p>
        <p>return ConnectionMultiplexer.Connect(cacheConnection);</p>
    <p>});</p>

    <p>public static ConnectionMultiplexer Connection</p>
    <p>{</p>
        <p>get</p>
        <p>{</p>
            <p>return lazyConnection.Value;</p>
        <p>}</p>
    <p>}</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-001/10.png"/>
<p>Once you connected to the cache, now execute the cache command by adding the following command for the Main procedure of the Program class for your console application.</p>
<p>static void Main(string[] args)</p>
<p>{</p>
    <p>// Connection refers to a property that returns a ConnectionMultiplexer</p>
    <p>// as shown in the previous example.</p>
    <p>IDatabase cache = lazyConnection.Value.GetDatabase();</p>

    <p>// Perform cache operations using the cache object...</p>

    <p>// Simple PING command</p>
    <p>string cacheCommand = "PING";</p>
    <p>Console.WriteLine("\nCache command  : " + cacheCommand);</p>
    <p>Console.WriteLine("Cache response : " + cache.Execute(cacheCommand).ToString());</p>

    <p>// Simple get and put of integral data types into the cache</p>
    <p>cacheCommand = "GET Message";</p>
    <p>Console.WriteLine("\nCache command  : " + cacheCommand + " or StringGet()");</p>
    <p>Console.WriteLine("Cache response : " + cache.StringGet("Message").ToString());</p>

    <p>cacheCommand = "SET Message \"Hello! The cache is working from a .NET console app!\"";</p>
    <p>Console.WriteLine("\nCache command  : " + cacheCommand + " or StringSet()");</p>
    <p>Console.WriteLine("Cache response : " + cache.StringSet("Message", "Hello! The cache is working from a .NET console app!").ToString());</p>

    <p>// Demonstrate "SET Message" executed as expected...</p>
    <p>cacheCommand = "GET Message";</p>
    <p>Console.WriteLine("\nCache command  : " + cacheCommand + " or StringGet()");</p>
    <p>Console.WriteLine("Cache response : " + cache.StringGet("Message").ToString());</p>

    <p>// Get the client list, useful to see if connection list is growing...</p>
    <p>cacheCommand = "CLIENT LIST";</p>
    <p>Console.WriteLine("\nCache command  : " + cacheCommand);</p>
    <p>Console.WriteLine("Cache response : \n" + cache.Execute("CLIENT", "LIST").ToString().Replace("id=", "id="));</p>

    <p>lazyConnection.Value.Dispose();</p>
<p>}</p>

<img src="https://codesizzlergit.blob.core.windows.net/az203-5-001/11.png"/>
<p>Once you execute the cache, now Press Ctrl+F5 to build and run the console app.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-001/12.png"/>
