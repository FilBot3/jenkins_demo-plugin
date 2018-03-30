# Jenkins Plugin Example

Resource: [Jenkins Plugin Development Tutorial](https://jenkins.io/doc/developer/tutorial/)

Right now, the last bit of the tutorial is having issues with the few Jelly lines

```xml
<st:include page="sidepanel.jelly" it="${it.run}" optional="true" />
```

When that line is removed, the stack trace goes away. With the line in the index.jelly file, the stack traces is as follows.


```
A problem occurred while processing the request. Please check our bug tracker to see if a
similar problem has already been reported. If it is already reported, please vote and put
a comment on it to let us gauge the impact of the problem. If you think this is a new
issue, please file a new issue. When you file an issue, make sure to add the entire stack
trace, along with the version of Jenkins and relevant plugins. The users list might be
also useful in understanding what has happened.

Stack trace

javax.servlet.ServletException: org.apache.commons.jelly.JellyException: Could not parse Jelly script : file:/C:/Users/Phillip/Desktop/jenkins_learning/demo-plugin/src/main/resources/io/jenkins/plugins/sample/HelloWorldAction/index.jelly
  at org.kohsuke.stapler.jelly.JellyClassTearOff.serveIndexJelly(JellyClassTearOff.java:117)
  at org.kohsuke.stapler.jelly.JellyFacet.handleIndexRequest(JellyFacet.java:127)
  at org.kohsuke.stapler.Stapler.tryInvoke(Stapler.java:735)
  at org.kohsuke.stapler.Stapler.invoke(Stapler.java:876)
  at org.kohsuke.stapler.MetaClass$11.dispatch(MetaClass.java:380)
  at org.kohsuke.stapler.Stapler.tryInvoke(Stapler.java:746)
  at org.kohsuke.stapler.Stapler.invoke(Stapler.java:876)
  at org.kohsuke.stapler.MetaClass$11.dispatch(MetaClass.java:380)
  at org.kohsuke.stapler.Stapler.tryInvoke(Stapler.java:746)
  at org.kohsuke.stapler.Stapler.invoke(Stapler.java:876)
  at org.kohsuke.stapler.MetaClass$5.doDispatch(MetaClass.java:233)
  at org.kohsuke.stapler.NameBasedDispatcher.dispatch(NameBasedDispatcher.java:58)
  at org.kohsuke.stapler.Stapler.tryInvoke(Stapler.java:746)
  at org.kohsuke.stapler.Stapler.invoke(Stapler.java:876)
  at org.kohsuke.stapler.Stapler.invoke(Stapler.java:649)
  at org.kohsuke.stapler.Stapler.service(Stapler.java:238)
  at javax.servlet.http.HttpServlet.service(HttpServlet.java:790)
  at org.eclipse.jetty.servlet.ServletHolder.handle(ServletHolder.java:841)
  at org.eclipse.jetty.servlet.ServletHandler$CachedChain.doFilter(ServletHandler.java:1650)
  at hudson.util.PluginServletFilter$1.doFilter(PluginServletFilter.java:135)
  at hudson.util.PluginServletFilter.doFilter(PluginServletFilter.java:126)
  at org.eclipse.jetty.servlet.ServletHandler$CachedChain.doFilter(ServletHandler.java:1637)
  at hudson.security.csrf.CrumbFilter.doFilter(CrumbFilter.java:49)
  at org.eclipse.jetty.servlet.ServletHandler$CachedChain.doFilter(ServletHandler.java:1637)
  at hudson.security.ChainedServletFilter$1.doFilter(ChainedServletFilter.java:84)
  at hudson.security.ChainedServletFilter.doFilter(ChainedServletFilter.java:76)
  at hudson.security.HudsonFilter.doFilter(HudsonFilter.java:171)
  at org.eclipse.jetty.servlet.ServletHandler$CachedChain.doFilter(ServletHandler.java:1637)
  at org.kohsuke.stapler.compression.CompressionFilter.doFilter(CompressionFilter.java:49)
  at org.eclipse.jetty.servlet.ServletHandler$CachedChain.doFilter(ServletHandler.java:1637)
  at hudson.util.CharacterEncodingFilter.doFilter(CharacterEncodingFilter.java:82)
  at org.eclipse.jetty.servlet.ServletHandler$CachedChain.doFilter(ServletHandler.java:1637)
  at org.kohsuke.stapler.DiagnosticThreadNameFilter.doFilter(DiagnosticThreadNameFilter.java:30)
  at org.eclipse.jetty.servlet.ServletHandler$CachedChain.doFilter(ServletHandler.java:1637)
  at org.eclipse.jetty.servlet.ServletHandler.doHandle(ServletHandler.java:533)
  at org.eclipse.jetty.server.handler.ScopedHandler.handle(ScopedHandler.java:143)
  at org.eclipse.jetty.security.SecurityHandler.handle(SecurityHandler.java:524)
  at org.eclipse.jetty.server.handler.HandlerWrapper.handle(HandlerWrapper.java:132)
  at org.eclipse.jetty.server.handler.ScopedHandler.nextHandle(ScopedHandler.java:190)
  at org.eclipse.jetty.server.session.SessionHandler.doHandle(SessionHandler.java:1595)
  at org.eclipse.jetty.server.handler.ScopedHandler.nextHandle(ScopedHandler.java:188)
  at org.eclipse.jetty.server.handler.ContextHandler.doHandle(ContextHandler.java:1253)
  at org.eclipse.jetty.server.handler.ScopedHandler.nextScope(ScopedHandler.java:168)
  at org.eclipse.jetty.servlet.ServletHandler.doScope(ServletHandler.java:473)
  at org.eclipse.jetty.server.session.SessionHandler.doScope(SessionHandler.java:1564)
  at org.eclipse.jetty.server.handler.ScopedHandler.nextScope(ScopedHandler.java:166)
  at org.eclipse.jetty.server.handler.ContextHandler.doScope(ContextHandler.java:1155)
  at org.eclipse.jetty.server.handler.ScopedHandler.handle(ScopedHandler.java:141)
  at org.eclipse.jetty.server.handler.ContextHandlerCollection.handle(ContextHandlerCollection.java:219)
  at org.eclipse.jetty.server.handler.HandlerCollection.handle(HandlerCollection.java:126)
  at org.eclipse.jetty.server.handler.HandlerWrapper.handle(HandlerWrapper.java:132)
  at org.eclipse.jetty.server.Server.handle(Server.java:564)
  at org.eclipse.jetty.server.HttpChannel.handle(HttpChannel.java:317)
  at org.eclipse.jetty.server.HttpConnection.onFillable(HttpConnection.java:251)
  at org.eclipse.jetty.io.AbstractConnection$ReadCallback.succeeded(AbstractConnection.java:279)
  at org.eclipse.jetty.io.FillInterest.fillable(FillInterest.java:110)
  at org.eclipse.jetty.io.ChannelEndPoint$2.run(ChannelEndPoint.java:124)
  at org.eclipse.jetty.util.thread.Invocable.invokePreferred(Invocable.java:128)
  at org.eclipse.jetty.util.thread.Invocable$InvocableExecutor.invoke(Invocable.java:222)
  at org.eclipse.jetty.util.thread.strategy.EatWhatYouKill.doProduce(EatWhatYouKill.java:294)
  at org.eclipse.jetty.util.thread.strategy.EatWhatYouKill.run(EatWhatYouKill.java:199)
  at org.eclipse.jetty.util.thread.QueuedThreadPool.runJob(QueuedThreadPool.java:672)
  at org.eclipse.jetty.util.thread.QueuedThreadPool$2.run(QueuedThreadPool.java:590)
  at java.lang.Thread.run(Thread.java:748)
Caused by: org.apache.commons.jelly.JellyException: Could not parse Jelly script : file:/C:/Users/Phillip/Desktop/jenkins_learning/demo-plugin/src/main/resources/io/jenkins/plugins/sample/HelloWorldAction/index.jelly
  at org.apache.commons.jelly.JellyContext.compileScript(JellyContext.java:529)
  at org.kohsuke.stapler.jelly.JellyClassTearOff.parseScript(JellyClassTearOff.java:56)
  at org.kohsuke.stapler.jelly.JellyClassTearOff.parseScript(JellyClassTearOff.java:47)
  at org.kohsuke.stapler.AbstractTearOff.resolveScript(AbstractTearOff.java:91)
  at org.kohsuke.stapler.jelly.JellyClassTearOff.resolveScript(JellyClassTearOff.java:94)
  at org.kohsuke.stapler.jelly.JellyClassTearOff.resolveScript(JellyClassTearOff.java:47)
  at org.kohsuke.stapler.AbstractTearOff.loadScript(AbstractTearOff.java:97)
  at org.kohsuke.stapler.CachingScriptLoader.findScript(CachingScriptLoader.java:60)
  at org.kohsuke.stapler.jelly.JellyClassTearOff.serveIndexJelly(JellyClassTearOff.java:102)
  ... 63 more
Caused by: org.xml.sax.SAXParseException; systemId: file:/C:/Users/Phillip/Desktop/jenkins_learning/demo-plugin/src/main/resources/io/jenkins/plugins/sample/HelloWorldAction/index.jelly; lineNumber: 5; columnNumber: 75; The prefix "st" for element "st:include" is not bound.
  at com.sun.org.apache.xerces.internal.util.ErrorHandlerWrapper.createSAXParseException(ErrorHandlerWrapper.java:203)
  at com.sun.org.apache.xerces.internal.util.ErrorHandlerWrapper.fatalError(ErrorHandlerWrapper.java:177)
  at com.sun.org.apache.xerces.internal.impl.XMLErrorReporter.reportError(XMLErrorReporter.java:400)
  at com.sun.org.apache.xerces.internal.impl.XMLErrorReporter.reportError(XMLErrorReporter.java:327)
  at com.sun.org.apache.xerces.internal.impl.XMLErrorReporter.reportError(XMLErrorReporter.java:284)
  at com.sun.org.apache.xerces.internal.impl.XMLNSDocumentScannerImpl.scanStartElement(XMLNSDocumentScannerImpl.java:284)
  at com.sun.org.apache.xerces.internal.impl.XMLDocumentFragmentScannerImpl$FragmentContentDriver.next(XMLDocumentFragmentScannerImpl.java:2784)
  at com.sun.org.apache.xerces.internal.impl.XMLDocumentScannerImpl.next(XMLDocumentScannerImpl.java:602)
  at com.sun.org.apache.xerces.internal.impl.XMLNSDocumentScannerImpl.next(XMLNSDocumentScannerImpl.java:112)
  at com.sun.org.apache.xerces.internal.impl.XMLDocumentFragmentScannerImpl.scanDocument(XMLDocumentFragmentScannerImpl.java:505)
  at com.sun.org.apache.xerces.internal.parsers.XML11Configuration.parse(XML11Configuration.java:842)
  at com.sun.org.apache.xerces.internal.parsers.XML11Configuration.parse(XML11Configuration.java:771)
  at com.sun.org.apache.xerces.internal.parsers.XMLParser.parse(XMLParser.java:141)
  at com.sun.org.apache.xerces.internal.parsers.AbstractSAXParser.parse(AbstractSAXParser.java:1140)
  at com.sun.org.apache.xerces.internal.jaxp.SAXParserImpl$JAXPSAXParser.parse(SAXParserImpl.java:655)
  at org.apache.commons.jelly.parser.XMLParser.parse(XMLParser.java:350)
  at org.apache.commons.jelly.JellyContext.compileScript(JellyContext.java:525)
  ... 71 more
```