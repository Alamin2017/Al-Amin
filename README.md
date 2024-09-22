👋 Hi, I'm Al-Amin from Bangladesh.

🌱 I’m working on Automation testing frameworks like Selenium, and Cypress.

👨‍💻 All of my projects are available at https://github.com/Alamin2017?tab=repositories

💞️ I’m looking to collaborate with...

📫 How to reach me 
alamincse12@gmail.com

Automation related document :

What is Appium: 

Appium is an open-source test automation framework for use with native, hybrid, and mobile apps.
It drives Android, iOS apps using the WebDriver protocol.

Need to Install software for setting up Environment Appium with Java for Mobile Application Automation:

→JAVA JDK Latest versions like 11,17,20

→Android Studio Latest Version

→Appium Windows Server with Latest Release

→IntelliJ IDEA Editor tool  

1.  Download and install Java (JDK) (https://www.oracle.com/in/java/technologies/downloads/#jdk17-windows) and set a path of JDK and bin folder with System variables:

→Go to the Environment variables and set variable name, value, and path in the System Variables 

Example: Variable name: JAVA_HOME and Variable value: C:\Program Files\Java\jdk-17 and Path : C:\Program Files\Java\jdk-17\bin.

->[Build Management Tool]-Download and Install Maven(https://maven.apache.org/download.cgi) and Configure it with System Variables and also include some paths in Path Variables.

Example: Variable name: Maven_HOME and Variable value: C:\Program Files\Java\apache-maven-3.8.7 and Path : C:\Program Files\Java\apache-maven-3.8.7\bin

->[Build Management Tool]-Download and Install Gradle(https://gradle.org/releases/) and Configure it with System Variables and also include some paths in Path Variables.

Example: Variable name: Gradle_HOME and Variable value: C:\Program Files\Java\gradle-7.6 and Path : C:\Program Files\Java\gradle-7.6\bin



2. Download and install Android Studio ( https://developer.android.com/studio?gclid=Cj0KCQiA8t2eBhDeARIsAAVEga1SBQMXg-rlpqz9RL7k_-Ip6a-_KEcFPmh2yPa3685chSPUdo2awMsaAuHtEALw_wcB&gclsrc=aw.ds) and Configure it with System Variables for Android SDK and also include some paths in Path Variables.

Example: Variable name: ANDROID_HOME and Variable value: C:\Users\amin.al\AppData\Local\Android\Sdk and Path : C:\Users\amin.al\AppData\Local\Android\Sdk\tools , C:\Users\amin.al\AppData\Local\Android\Sdk\emulator , C:\Users\amin.al\AppData\Local\Android\Sdk\platform-tools



3. Download and install Appium Windows Server like v1.21.0b from the GitHub link: https://github.com/appium/appium-desktop/releases/tag/v1.21.0 and Configure it System Variables in Path Variables.

Path: C:\Program Files\Appium\resources\app\node_modules



4. Open the Appium Windows Server and Go to the Edit Configurations and setup path for Android_HOME and JAVA_HOME



5. Download and Install IntelliJ IDEA(Community Edition) from https://www.jetbrains.com/idea/download/#section=windows



Download and Install Nodejs (https://nodejs.org/en/download/), Configure it with System Variables, and include some Path Variables.
Example: Variable name: NODE_JS and Variable value: C:\Program Files\nodejs and Path : C:\Program Files\nodejs\node_modules , C:\Program Files\nodejs\node_modules\npm ,C:\Program Files\nodejs\node_modules\npm\bin.



How to find out app package and app activity and other info for appium java

1. open cmd and push "adb devices" to find out UDID.

2. push "adb shell dumpsys window | find "mCurrentFocus" "

com.samsung.android.shealthmonitor/com.samsung.android.shealthmonitor.ui.activity.MainActivity

mobile_driver.terminateApp("com.samsung.android.shealthmonitor");->just close app after one test
mobile_driver.removeApp("com.samsung.android.shealthmonitor");->uninstalled app after test
mobile_driver.activateApp("com.samsung.android.shealthmonitor");-> just open app after installed app
mobile_driver.installApp("C:\\Users\\amin.al\\Desktop\\certificate\\Fake_Country_App_BP_ECG_IHRN_1.2.1.005.apk"); install app first time

Mobile Browser automates in Appium:
https://stackoverflow.com/questions/52023111/no-chromedriver-found-that-can-automate-chrome-53-0-2785
https://www.swtestacademy.com/how-to-install-appium-on-mac/
Gradle_dependancy _workable for all:

testImplementation group: 'org.testng', name: 'testng', version: '7.8.0'
implementation group: 'org.seleniumhq.selenium', name: 'selenium-server', version: '3.141.59'
implementation group: 'io.appium', name: 'java-client', version: '7.6.0'

Need to certificate permissions:

https://sanaebadi97.medium.com/solve-the-certificate-error-in-android-studio-5773551e97f3


Go to C:\Program Files\Java\jdk-17\bin  and open administrator-cmd →run below commad

keytool -import -alias example -keystore "C:\Program Files\Java\jdk-17\lib\security\cacerts" -file C:\Users\amin.al\Desktop\certificate\siel.crt
password :changeit

yes

Watch app run by appium server:
{
  "app": "C:\\Users\\amin.al\\Desktop\\certificate\\SHealthMonitor_Wear_Emulator_1.2.1.004.apk",
  "platformName": "Android",
  "appPackage": "com.samsung.android.shealthmonitor",
  "appActivity": "com.samsung.android.shealthmonitor.ui.activity.MainActivity"
}
Phone app run by appium server:
{
  "platformName": "Android",
  "appium:app": "C:\\Users\\amin.al\\Desktop\\certificate\\Fake_Country_App_BP_ECG_IHRN_1.2.1.005.apk",
  "appium:deviceName": "Galaxy S20 5G ",
  "appium:udid": "R3CMB0JA79M"
}
values.get(0).click();
TouchAction action= new TouchAction(mobile_driver);
action.press(PointOption.point(523,1825)).release().perform();
Thread.sleep(1000);

values.get(0).sendKeys("MAY");
values.get(1).sendKeys("08");
values.get(2).sendKeys("2000");
mobile_driver.findElement(
                MobileBy.AndroidUIAutomator(
                        "new UiScrollable(new UiSelector()).scrollIntoView("
                                + "new UiSelector().text(\"APR, Month\"));"));

mobile_driver.findElement(MobileBy.AndroidUIAutomator(
                "new UiScrollable(new UiSelector().scrollable(true)).setAsVerticalList()" +
                        ".scrollIntoView(new UiSelector().text(\"NOV\"))"));

scrollClick:
mobile_driver.findElement(MobileBy.AndroidUIAutomator("new UiScrollable(new UiSelector().scrollable(true).instance(0)).setAsHorizontalList().scrollIntoView(new UiSelector().text(\""+textToSearch+"\"))")).click();

10 times down:
mobile_driver.findElement(MobileBy.AndroidUIAutomator("new UiScrollable(new UiSelector().scrollable(true).instance(0)).scrollToEnd(10);"));
10 times up:
mobile_driver.findElement(MobileBy.AndroidUIAutomator("new UiScrollable(new UiSelector().scrollable(true).instance(0)).scrollToBeginning(10);"));

    public static void swipe_down_watch() {
        AndroidTouchAction touchAction = new AndroidTouchAction((PerformsTouchActions) watch_driver);
        Dimension dimension = watch_driver.manage().window().getSize();
        int start_x = (int) (dimension.width) / 2;
        int start_y = (int) (dimension.height * 8) / 9;
        int end_x = (int) (dimension.width) / 2;
        int end_y = (int) (dimension.height) / 9;
        touchAction.press(PointOption.point(start_x, start_y)).waitAction(WaitOptions.waitOptions(Duration.ofSeconds(1))).moveTo(PointOption.point(end_x, end_y)).release().perform();
    }
    public static void swipe_up_watch() {
        AndroidTouchAction touchAction = new AndroidTouchAction((PerformsTouchActions) watch_driver);
        Dimension dimension = watch_driver.manage().window().getSize();
        int start_x = (int) (dimension.width) / 2;
        int start_y = (int) (dimension.height * 2) / 9;
        int end_x = (int) (dimension.width) / 2;
        int end_y = (int) (dimension.height * 8) / 9;
        touchAction.press(PointOption.point(start_x, start_y)).waitAction(WaitOptions.waitOptions(Duration.ofSeconds(1))).moveTo(PointOption.point(end_x, end_y)).release().perform();
    }
    public static void HOME_Key() throws IOException, InterruptedException {
        String cmd = "adb shell input keyevent 3";
        Runtime.getRuntime().exec(cmd);
        Thread.sleep(3000);
    }
    public static void App_Switch_Key() throws IOException, InterruptedException {
        String cmd = "adb shell input keyevent 187";
        Runtime.getRuntime().exec(cmd);
        Thread.sleep(3000);
    }

    public static AndroidDriver mobile_driver;

    @BeforeMethod
    public void Setup() throws InterruptedException, MalformedURLException {
        DesiredCapabilities cap = new DesiredCapabilities();
        cap.setCapability(MobileCapabilityType.AUTOMATION_NAME, "UiAutomator2");
        cap.setCapability(MobileCapabilityType.DEVICE_NAME, "Galaxy S10e");
        cap.setCapability(MobileCapabilityType.PLATFORM_NAME, "Android");
        cap.setCapability(MobileCapabilityType.UDID, "R38KB0QN46M");
        cap.setCapability(MobileCapabilityType.NEW_COMMAND_TIMEOUT,600);
        URL url = new URL("http://127.0.0.1:4723/wd/hub");
        mobile_driver = new AndroidDriver(url, cap);
        Thread.sleep(2000);
        mobile_driver.installApp("C:\\Users\\amin.al\\Desktop\\certificate\\Fake_Country_App_BP_ECG_IHRN_1.2.1.005.apk");
        Thread.sleep(2000);
        mobile_driver.activateApp("com.samsung.android.shealthmonitor");
        Thread.sleep(2000);
    }

    public static WebDriver driver;
    @Test
    public void test_mobile_browser() throws InterruptedException, MalformedURLException {
        ChromeOptions options=new ChromeOptions();
        URL url=new URL("http://127.0.0.1:4723/wd/hub");
        options.setCapability(MobileCapabilityType.PLATFORM_NAME,"Android");
        options.setCapability(MobileCapabilityType.UDID, "R38KB0QN46M");
        driver=new AndroidDriver(url,options);
        driver.get("https://eticket.railway.gov.bd/");
        Thread.sleep(5000);
        driver.findElement(By.xpath("//button[normalize-space()='I Agree']")).click();
        Thread.sleep(5000);
        driver.close();
    }

Data Manipulation for jsondata:

JSONParser jsonparser=new JSONParser();
FileReader reader=new FileReader("C:\\Users\\amin.al\\IdeaProjects\\WebAutomation\\data\\data.json");
Object obj=jsonparser.parse(reader);
JSONObject userloginsJsonobj=(JSONObject)obj;
JSONArray userloginsArray=(JSONArray)userloginsJsonobj.get("userlogins");

System.out.println("data:1");
JSONObject users0=(JSONObject) userloginsArray.get(0);

System.out.println(users0);
System.out.println(users0.get("username"));
System.out.println(users0.get("password"));
System.out.println(users0.get("district"));

LongPress for element:
TouchAction action=new TouchAction(mobile_driver);
action.longPress(LongPressOptions.longPressOptions().withElement(ElementOption.element(SHM)).withDuration(Duration.ofMillis(500))).release().perform();
mobile_driver.findElement(By.xpath("//android.widget.ImageView[@content-desc=\"App info\"]")).click();

SwipeLeftScreen::
public static void SwipeLeftScreenOngoingImplement() {
        AndroidTouchAction touchAction = new AndroidTouchAction((PerformsTouchActions) watch_driver);
        Dimension dimension = watch_driver.manage().window().getSize();
        int start_x = (int) ((dimension.width) * 0.90);
        int start_y = (int) ((dimension.height) / 2);
        int end_x = (int) ((dimension.width) * 0.05);
        int end_y = 0;
        touchAction.press(PointOption.point(start_x, start_y)).waitAction(WaitOptions.waitOptions(Duration.ofSeconds(1))).moveTo(PointOption.point(end_x, end_y)).release().perform();
}
How to read json data :

public class JSONDataRead {
    private String email;
    private String password;
    public String getEmail() {
        return email;
    }
    public String getPassword() {
        return password;
    }
    public void setEmail(String email) {
        this.email = email;
    }
    public void setPassword(String password) {
        this.password = password;
    }
    public void getUserCreds(int pos) throws IOException, ParseException, org.json.simple.parser.ParseException {
        String fileName="C:\\Users\\hp\\IdeaProjects\\jdk17check\\src\\test\\java\\testdata\\users.json";
        JSONParser jsonParser=new JSONParser();
        Object obj=jsonParser.parse(new FileReader(fileName));
        JSONArray jsonArray=(JSONArray) obj;
        JSONObject jsonObject=(JSONObject) jsonArray.get(pos);
        setEmail((String)jsonObject.get("email"));
        setPassword((String)jsonObject.get("password"));
    }
}
JSONDataRead data_json=new JSONDataRead();

# if you want to configure triggers for Azure CI see

jobs:
  - job: Cypress_E2E_Test
    pool:
      vmImage: 'ubuntu-latest'
    strategy:
      parallel: 1
    steps:
      - task: NodeTool@0
        inputs:
          versionSpec: '18.x'
          displayName: 'Install Node.js'
      # Install Node dependencies
      - script: npm ci
        displayName: 'Install NPM dependencies'

      - script: |
      
          npm install cypress --save-dev
          npx cypress run
        displayName: 'Run Cypress E2E Test'
        env:
          # avoid warnings about terminal
          TERM: xterm
          # map the secret Cypress record key as environment variable for this step
          CYPRESS_RECORD_KEY: $(CYPRESS_RECORD_KEY)
        
 const { defineConfig } = require("cypress");

module.exports = defineConfig({
  projectId: 'iqjavs',

  e2e: {
    watchForFileChanges:false,
    defaultCommandTimeout:30000,
    requestTimeout:30000,
    responseTimeout:60000,
    viewportWidth:1280,
    viewportHeight:720,
    video:false,
    chromeWebSecurity:false,
    setupNodeEvents(on, config) {
      // implement node event listeners here
      screenshotOnRunFailure=true;
    },
    
    testIsolation: false
  },
});

describe('URL browsing and saving test', () => { const search_keyword_worklist=["work","worklist"]; it('Browses URLs and saves them in JSON format', () => { cy.visit("https://unifytest.julyservices.local/Unify.V2.Web/login"); login_obj.username_text_field().type("alamin"); login_obj.password_text_field().type("123"); login_obj.login_button().click(); home_obj.open_main_menu_button().click(); const dataToSave = {}; search_keyword_worklist.forEach((search_keyword)=>{ const visitedUrls=[]; drawer_obj.looking_for_search_field().type(search_keyword); const total_worklist=drawer_obj.worklist_search_item_count(); total_worklist.its('length').then(length=>{ for(let i=0;i<length;i++){ drawer_obj.worklist_search_item_count().eq(i).click(); cy.url().then(url=>{ visitedUrls.push(url); }); cy.wait(1000); home_obj.open_main_menu_button().click(); cy.wait(1000); } }); dataToSave[search_keyword] = visitedUrls; visitedUrls.length = 0; drawer_obj.looking_for_search_field().clear(); }); cy.writeFile('visited_urls_keyword_basis.json', dataToSave) drawer_obj.close_button().click(); }); });



describe('URL browsing and saving test', () => { const search_keyword_worklist=["work","worklist"]; it('Browses URLs and saves them in JSON format', () => { cy.visit("https://unifytest.julyservices.local/Unify.V2.Web/login"); login_obj.username_text_field().type("alamin"); login_obj.password_text_field().type("123"); login_obj.login_button().click(); home_obj.open_main_menu_button().click(); const visitedUrls=[]; search_keyword_worklist.forEach((search_keyword)=>{ drawer_obj.looking_for_search_field().type(search_keyword); const total_worklist=drawer_obj.worklist_search_item_count(); total_worklist.its('length').then(length=>{ for(let i=0;i<length;i++){ drawer_obj.worklist_search_item_count().eq(i).click(); cy.url().then(url=>{ visitedUrls.push(url); }); cy.wait(1000); home_obj.open_main_menu_button().click(); cy.wait(1000); } }); drawer_obj.looking_for_search_field().clear(); }); const dataToSave = { visitedUrls: visitedUrls }; cy.writeFile('visited_urls.json', dataToSave) drawer_obj.close_button().click(); }); });
{
  "name": "cypress-pom",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "npx cypress open",
    "test:browser:headless": "npx cypress run --browser=chrome",
    "test:browser:headed": "npx cypress run --browser=chrome --headed",
    "browser:chrome:allure:pass": "npx cypress run --browser=chrome --headed --reporter mocha-allure-reporter && allure generate allure-results --clean -o allure-report && allure open allure-report",
    "test:allure:report:headed": "npx cypress run --browser=chrome --headed --reporter mocha-allure-reporter",
    "test:allure:report:headless": "npx cypress run --browser=chrome --reporter mocha-allure-reporter",
    "test:allure:result": "allure generate allure-results --clean -o allure-report && allure open allure-report"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "@faker-js/faker": "^8.4.0",
    "allure-commandline": "^2.30.0",
    "cypress": "^13.12.0",
    "cypress-localstorage-commands": "^2.2.6",
    "cypress-xpath": "^2.0.1",
    "mocha-allure-reporter": "^1.4.0"
  }
}
