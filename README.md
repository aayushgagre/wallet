"([A-Za-z]{3}[A-Za-z]* [A-Za-z]{3}[A-Za-z]*)|([A-Za-z]+'[A-Za-z]*[A-Za-z]{3}[A-Za-z])";












public static boolean validateDesignation(double salary, String desig)
	{
		if((salary>5000 && salary <20000) && (desig.equalsIgnoreCase("system associate")))
			return true;
		
		if((salary>=20000 && salary<40000) && desig.equalsIgnoreCase("programmer"))
			return true;
		
		if((salary>=40000) && desig.equalsIgnoreCase("Manager"))
			return true;
		
		if(salary<5000 && desig.equalsIgnoreCase("clerk"))
			return true;
		
		else
			return false;
	}
