"# _**QA Testing**_ "
1. Initialize IE Mode in Edge browser through selenium code.

**Pre.Req:**

> Download IE driver.

> Get EDGE browser directory path

#Enable IE mode in Edge Browser in selenium JAVA code.

**Code:**

        System.setProperty("webdriver.ie.driver", <<IE-Driver-Path>>);
        InternetExplorerOptions edgeIe11Options = new InternetExplorerOptions();
        Map<String, Object> ops = (Map<String, Object>) edgeIe11Options.getCapability("se:ieOptions");
        ops.put("ie.edgechromium", true);
        ops.put("ie.edgepath", "msedge.exe");     // _Edge Browser directory path_
 
        edgeIe11Options.introduceFlakinessByIgnoringSecurityDomains();
        edgeIe11Options.ignoreZoomSettings();
        edgeIe11Options.enablePersistentHovering();
        edgeIe11Options.takeFullPageScreenshot();
        edgeIe11Options.disableNativeEvents();
        edgeIe11Options.requireWindowFocus();
        edgeIe11Options.destructivelyEnsureCleanSession();

        edgeIe11Options.setCapability("ignoreProtectedModeSettings", true);
        edgeIe11Options.setUnhandledPromptBehaviour(UnexpectedAlertBehaviour.IGNORE);

        WebDriver driver;
        driver = new InternetExplorerDriver(edgeIe11Options);
        wait = new WebDriverWait(driver, 25);
        driver.get("https://github.com/");









