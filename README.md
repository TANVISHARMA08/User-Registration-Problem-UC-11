# User-Registration-Problem-UC-11
package assignment;
import java.util.Arrays;
import java.util.List;

import org.junit.Assert;
import org.junit.Test;
import org.junit.runner.RunWith;
import org.junit.runners.Parameterized;

@RunWith(Parameterized.class)
public class ParameterizedEmail {
  
	private String emailTest;
	private boolean expectedResult;
    
	
	public ParameterizedEmail(String input3,boolean expectedResult) {
		this.emailTest=input3;
		this.expectedResult=expectedResult;
		
	}
	
	@Parameterized.Parameters
	public static List<Object[]> input()
	{
		return Arrays.asList(new Object [][] {
			{"tanvi@yahoo.com",true},
			{"tanvi-100@yahoo.com",true},
			{"tanvi.100@yahoo.com",true},
			{"tanvi420@yahoo.com",true},
			{"tanvi-100@abc.net",true},
			{"tanvi-100@yahoo.abcgsgx",false},
			{"tanvi@1.com",true},
			{"tanvi100@yahoo.com.comyahoo",false}});
	}
	@Test
	public void givenEmailAsVar_ShouldReturnPerfectResult()
	{
		UserRegistration userRegistration=new UserRegistration();
		boolean result = userRegistration.checkemail(emailTest);
		Assert.assertEquals(expectedResult, result);
	}

}
