# Find Elements

Search for multiple elements
## Example Usage

```java
// Java
List<MobileElement> elementsOne = (MobileElement) driver.findElementsByAccessibilityId("SomeAccessibilityID");
List<MobileElement> elementsTwo = (MobileElement) driver.findElementsByClassName("SomeClassName");

```

```python
# Python
el = self.driver.find_elements_by_accessibility_id('SomeAccessibilityID')

```

```javascript
// Javascript
// webdriver.io example
driver.elements("~SomeAccessibilityId");



// wd example
let elementsOne = await driver.elementsByAccessibilityId("SomeAccessibilityID");
let elementsTwo = await driver.elements("id", "SomeID");

```

```ruby
# Ruby
@driver.find_elements("~SomeAccessibilityID")

```

```php
# PHP
// TODO PHP sample

```

```csharp
// C#
// TODO C# sample

```

## Selector Strategies
|Strategy|Description|
|--------|-----------|
|Accessibility ID|Read a unique identifier for a UI element. For XCUITest it is the element's `resource-id` attribute. For Android it is the element's `content-desc` attribute.|
|Class name|For IOS it is the full name of the XCUI element and begins with XCUIElementType. For Android it is the full name of the UIAutomator2 class (e.g.: android.widget.TextView)|
|ID|Native element identifier. For Android it is|
|Name|Name of element|
|XPath|Search the app XML source using xpath (not recommended, has performance issues)|
|Android UiAutomator|Use the UI Automator API, in particular the UiSelector class to locate elements. In Appium you send the Java code, as a string, to the server, which executes it in the application’s environment, returning the element or elements.|
|IOS UIAutomation|When automating an iOS application, Apple’s UI Automation framework can be used to find elements|

## Description

Get a list of elements that match the [locator selector](/docs/en/about-appium/getting-started.md).


## Support

### Appium Server

|Platform|Driver|Platform Versions|Appium Version|Driver Version|
|--------|----------------|------|--------------|--------------|
| iOS | [XCUITest](/docs/en/drivers/ios-xcuitest.md) | 9.3+ | 1.6.0+ | All |
|  | [UIAutomation](/docs/en/drivers/ios-uiautomation.md) | 8.0 to 9.3 | All | All |
| Android | [UiAutomator2](/docs/en/drivers/android-uiautomator2.md) | ?+ | 1.6.0+ | All |
|  | [UiAutomator](/docs/en/drivers/android-uiautomator.md) | 4.2+ | All | All |
| Mac | [Mac](/docs/en/drivers/mac.md) | ?+ | 1.6.4+ | All |
| Windows | [Windows](/docs/en/drivers/windows.md) | 10+ | 1.6.0+ | All |

### Appium Clients

|Language|Support|Documentation|
|--------|-------|-------------|
|[Java](https://github.com/appium/java-client/releases/latest)| All |  [seleniumhq.github.io](https://seleniumhq.github.io/selenium/docs/api/java/org/openqa/selenium/WebElement.html#findElements-org.openqa.selenium.By-)  |
|[Python](https://github.com/appium/python-client/releases/latest)| All |  [selenium-python.readthedocs.io](http://selenium-python.readthedocs.io/api.html#selenium.webdriver.remote.webdriver.WebDriver.find_elements)  |
|[Javascript (WebdriverIO)](http://webdriver.io/index.html)| All |  [webdriver.io](http://webdriver.io/api/protocol/elements.html#Usage)  |
|[Javascript (WD)](https://github.com/admc/wd/releases/latest)| All |  [github.com](https://github.com/admc/wd/blob/master/lib/commands.js#L798)  |
|[Ruby](https://github.com/appium/ruby_lib/releases/latest)| All |  [www.rubydoc.info](http://www.rubydoc.info/gems/selenium-webdriver/Selenium/WebDriver/SearchContext:find_elements)  |
|[PHP](https://github.com/appium/php-client/releases/latest)| All |  [github.com](https://github.com/appium/php-client/)  |
|[C#](https://github.com/appium/appium-dotnet-driver/releases/latest)| All |  [github.com](https://github.com/appium/appium-dotnet-driver/)  |

## HTTP API Specifications

### Endpoint

`POST /wd/hub/session/:session_id/elements`

### URL Parameters

|name|description|
|----|-----------|
|session_id|ID of the session to route the command to|

### JSON Parameters

|name|type|description|
|----|----|-----------|
| using | `string` | The locator strategy to use |
| value | `string` | The search target |

### Response

A list of of JSON objects for the located elements (`Array<String>`)

## See Also

* [W3C Specification](https://www.w3.org/TR/webdriver/#dfn-find-elements)
* [JSONWP Specification](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelements)
