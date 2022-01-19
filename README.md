#Demo

this project is used to test some random website.
i wanted to change my scripts.
package newpackage;

import java.util.Iterator;
import java.util.Set;

import org.openqa.selenium.Alert;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
public class Assignment {
	public static void main(String[] args) throws InterruptedException {
		
	
	System.setProperty("webdriver.chrome.driver","C:\\Drivers\\chromedriver.exe");
	//System.setProperty("webdriver.chrome.driver", "C:\\Drivers\\chromedriver.exe");
WebDriver driver=new ChromeDriver();
driver.get("https://rahulshettyacademy.com/AutomationPractice/"); //to open browser
driver.manage().window().maximize();
Thread.sleep(2000);
driver.findElement(By.xpath("//*[@id=\"radio-btn-example\"]/fieldset/label[3]/input")).click();
Thread.sleep(2000);
driver.findElement(By.id("autocomplete")).sendKeys("Zambia");
Thread.sleep(2000);
driver.findElement(By.xpath("//*[@id=\"dropdown-class-example\"]/option[2]")).click();
Thread.sleep(2000);
driver.findElement(By.id("checkBoxOption1")).click();
driver.findElement(By.id("checkBoxOption2")).click();
Thread.sleep(2000);
driver.findElement(By.name("checkBoxOption3")).click();
Thread.sleep(2000);
//driver.getWindowHandle();
//driver.findElement(By.id("opentab")).click();
driver.findElement(By.id("name")).sendKeys("supriya");
Thread.sleep(2000);
driver.findElement(By.id("alertbtn")).click();
Thread.sleep(2000);
Alert alert=driver.switchTo().alert();
String alertMessage=driver.switchTo().alert().getText();
System.out.println(alertMessage);
alert.accept();
Thread.sleep(2000);
driver.findElement(By.id("confirmbtn")).click();
alert.accept();
driver.findElement(By.id("displayed-text")).sendKeys("nutte");
Thread.sleep(2000);
driver.findElement(By.id("hide-textbox")).click();
Thread.sleep(2000);
driver.findElement(By.id("show-textbox")).click();
Thread.sleep(2000);
WebElement ToGetColumns = driver.findElement(By.xpath("//table[@id='product']/tbody/tr"));

java.util.List<WebElement> TotalColsList = ToGetColumns.findElements(By.tagName("th"));

System.out.println("Total Number of Columns in the table are: "+TotalColsList.size());
driver.findElement(By.className("btn btn-primary")).click();
Thread.sleep(2000);
driver.findElement(By.id("openwindow")).click();
//Thread.sleep(2000);
//driver.close();
String parent=driver.getWindowHandle();

Set<String>s=driver.getWindowHandles();

// Now iterate using Iterator
java.util.Iterator<String> I1= s.iterator();

while(I1.hasNext())
{

String child_window=I1.next();


if(!parent.equals(child_window))
{
driver.switchTo().window(child_window);

System.out.println(driver.switchTo().window(child_window).getTitle());

driver.close();
}
	}
	}
}
