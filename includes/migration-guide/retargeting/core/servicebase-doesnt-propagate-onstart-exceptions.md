### <a name="servicebase-doesnt-propagate-onstart-exceptions"></a>ServiceBase no propaga las excepciones OnStart

|   |   |
|---|---|
|Detalles|En .NET Framework 4.7 y versiones anteriores, las excepciones que se producen al inicio del servicio no se propagan al autor de la llamada de <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType>.<br/>A partir de las aplicaciones que tienen como destino .NET Framework 4.7.1, el tiempo de ejecución propaga las excepciones a <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> para los servicios que no se pueden iniciar.|
|Sugerencia|Durante el inicio del servicio, si hay una excepción, se propaga. Esto debería ayudar a diagnosticar los casos en los que no se pueden iniciar los servicios. <br/>Si no quiere este comportamiento, puede rechazarlo mediante la adición del elemento <AppContextSwitchOverrides> siguiente a la sección <runtime> del archivo de configuración de la aplicación:<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceProcess.DontThrowExceptionsOnStart=true&quot; /&gt;&#13;&#10;</code></pre>Si la aplicación está destinada a una versión anterior a 4.7.1 pero quiere tener este comportamiento, agregue el elemento <AppContextSwitchOverrides> siguiente a la sección <runtime> del archivo de configuración de la aplicación:<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceProcess.DontThrowExceptionsOnStart=false&quot; /&gt;&#13;&#10;</code></pre>|
|Ámbito|Secundaria|
|Versión|4.7.1|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.ServiceProcess.ServiceBase.Run(System.ServiceProcess.ServiceBase)?displayProperty=nameWithType></li><li><xref:System.ServiceProcess.ServiceBase.Run(System.ServiceProcess.ServiceBase[])?displayProperty=nameWithType></li></ul>|

