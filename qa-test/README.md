# Task
Use BDD and C# to write and automate the following scenario on http://amazon.com:

1. Search for a book
2. Add the book to the cart

Any BDD and browser-automation tool can be used, but SpecFlow and Selenium are strongly preferred.

How you structure the test is up to you, but will be taken into account when the code is assessed.

Feel free to add any comments to clarify areas you feel are confusing or that you wish to highlight. Also please include instructions for running the tests.


//Program in selenium webdrive

package own;
//Package name

import static org.junit.Assert.*;

import java.io.File;
import java.sql.Driver;
import java.util.concurrent.TimeUnit;
import java.util.stream.Stream;

import org.junit.After;
import org.junit.Before;
import org.junit.Test;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class table {
WebDriver driver;
private CharSequence book;
	@Before
	public void setUp() throws Exception {
		System.setProperty("webdriver.chrome.driver", "D:\\Srija\\selenium\\selenium\\chromedriver_win32\\chromedriver.exe");
		driver=new ChromeDriver();
		driver.manage().timeouts().implicitlyWait(30, TimeUnit.SECONDS);
	}

	@After
	public void tearDown() throws Exception {
		driver.close();
	}

	@Test
	public void test() {
		driver.get("http://www.amazon.com/");
		driver.findElement(By.id("twotabsearchtextbox")).sendKeys("book");
		driver.findElement(By.className("nav-input")).click();
		driver.findElement(By.xpath("/html/body/div[1]/div[1]/div[4]/div[2]/div/div[4]/div[1]/div/ul/li[1]/div/div/div/div[2]/div[1]/a/h2")).click();
		driver.findElement(By.id("add-to-cart-button")).click();	
	}

}
