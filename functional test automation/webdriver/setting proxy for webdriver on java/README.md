How to initialise Webdriver and RemoteWebdriver with custom Proxy
==================

1. This example described how to use proxy in IE, Chrome and Firefox
for WebDriver and RemoteWebDriver 
2. also in this example shown how to set proxy for Firefox via profile and Chrome via options


### Description

As an example in this article is used BrowserMobProxy which is started by locally. All traffic passed via this local proxy. 


* Set proxy for Chrome via RemoteWebDriver 
```java
        DesiredCapabilities capabilities = DesiredCapabilities.chrome();
        capabilities.setCapability(CapabilityType.PROXY, getProxy());
        driver = new RemoteWebDriver(new URL("http://localhost:4444/wd/hub"), capabilities);
```
* Set proxy for Chrome via WebDriver
```java
        DesiredCapabilities capabilities = new DesiredCapabilities();
        capabilities.setCapability(CapabilityType.PROXY, getProxy());
        driver = new ChromeDriver(capabilities);
```


If it need to use remote proxy, should be implemented appropriate REST client.
This example applied only for local proxy. BrowserMob proxy lib that is started locally.
