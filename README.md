# exp-11-seleniuminstall
Sure! Let's go step-by-step to **install Selenium and use it for automated testing in IntelliJ IDEA**. We'll use **Java** (most commonly used with Selenium).

---

## ✅ Goal:

We will:

1. Install and set up IntelliJ IDEA with Selenium.
2. Write a simple Selenium test in Java.
3. Run the test using ChromeDriver.

---

## 🧰 Prerequisites:

* **IntelliJ IDEA** installed
* **Java JDK** installed (Java 8 or above)
* **Chrome Browser**
* **ChromeDriver** matching your Chrome version

---

## 🔧 Step 1: Install IntelliJ IDEA & Java

### 1. Install IntelliJ IDEA:

* Download: [https://www.jetbrains.com/idea/download](https://www.jetbrains.com/idea/download)
* Use **Community Edition** (free)

### 2. Install Java JDK:

* Download JDK: [https://www.oracle.com/java/technologies/javase-downloads.html](https://www.oracle.com/java/technologies/javase-downloads.html)
* After install, confirm in terminal/cmd:

```bash
java -version
javac -version
```

---

## 🪛 Step 2: Create Java Project in IntelliJ

1. Open IntelliJ IDEA
2. Click **New Project**
3. Select **Java** → Click **Next**
4. Name it `SeleniumTestProject`
5. Click **Finish**

---

## 🧱 Step 3: Add Selenium Library to Your Project

### Option A: Using Maven (Recommended)

1. Right-click on your project → **Add Framework Support** → Select **Maven**
2. A file `pom.xml` will be created.
3. Add Selenium dependency inside `<dependencies>`:

```xml
<dependencies>
  <dependency>
    <groupId>org.seleniumhq.selenium</groupId>
    <artifactId>selenium-java</artifactId>
    <version>4.20.0</version>
  </dependency>
</dependencies>
```

4. IntelliJ will auto-download dependencies (wait for the build to finish).

---

## ⚙️ Step 4: Download ChromeDriver

1. Go to [https://chromedriver.chromium.org/downloads](https://chromedriver.chromium.org/downloads)
2. Download the version matching your Chrome browser.
3. Extract and place `chromedriver.exe` in a known path (e.g., `C:\drivers`)
4. Add that folder to **System PATH**.

### ✅ Test:

In Command Prompt:

```bash
chromedriver
```

You should see: `Starting ChromeDriver...` (don’t worry about error message)

---

## 🧪 Step 5: Write Your First Selenium Test

1. Right-click `src` folder → New → Java Class → Name it `LoginTest`
2. Paste this sample test:

```java
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class LoginTest {
    public static void main(String[] args) {
        // Set up path to ChromeDriver (optional if added to PATH)
        System.setProperty("webdriver.chrome.driver", "C:\\drivers\\chromedriver.exe");

        // Launch Chrome browser
        WebDriver driver = new ChromeDriver();

        // Open a test website
        driver.get("https://example.com"); // Replace with your login page

        // Find elements (example)
        WebElement heading = driver.findElement(By.tagName("h1"));
        System.out.println("Page heading: " + heading.getText());

        // Close browser
        driver.quit();
    }
}
```

> 🔁 You can modify the `driver.get()` URL and selectors (`By.id`, `By.name`, etc.) as per your target website or HTML form.

---

## ▶️ Step 6: Run the Test

1. Right-click on `LoginTest.java` → **Run**
2. Chrome will open and perform the automated test steps.

---

## 🧼 Optional: Organize with TestNG (for Test Suites)

Would you like to use **TestNG or JUnit** to create multiple test cases (suites)?
If yes, I can guide you on that too.

---

## ✅ Summary

You now have:

* IntelliJ Java project ✅
* Selenium added ✅
* ChromeDriver configured ✅
* Test case working ✅

---

Would you like help:

* Testing a real login form?
* Writing a full test suite?
* Running tests in **headless mode** (no browser window)?

Let me know — happy to assist!
