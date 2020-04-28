# Selenium Snippets
https://www.selenium.dev/

### Selenium Grid
Minimal code to execute a test on a Selenium grid  
Source: [Khyati Sehgal´s Bolg](https://khyatisehgal.wordpress.com/2014/08/24/selenium-gridorg-openqa-selenium-remote-unreachablebrowserexception-could-not-start-a-new-session-possible-causes-are-invalid-address-of-the-remote-server-or-browser-start-up-failure/)

```java
public class TestingSeleniumGrid {
    private WebDriver driver;
    @BeforeClass
    public void setUp() throws Exception {
        DesiredCapabilities capabilities = DesiredCapabilities.chrome();
//        capabilities.setCapability("platform", Platform.WINDOWS);
        driver = new RemoteWebDriver(new URL("http://localhost:4444/wd/hub"),capabilities);
    }

    @Test
    public void testSimple() throws Exception {
        driver.get("http://google.com");
    }

    @AfterClass
    public void tearDown() throws Exception {
        driver.quit();
    }
}
```