# Luhn-Algorithm
Checksum Validation Algorithm

#include <stdio.h>
#include <iostream>
#include <string>

using namespace std;

//For the valid inputs
bool isstringnumber(string s)
{
	for(int i=0;i<s.length();i++)
	{
		if(s[i]<'0' || s[i]>'9')
		{
			return false;
		}
		return true;
	}
}

int main()
{
	//Here, we are taking the inputs in the sting format
	//so, we have to take the difference with 48 (ASCII value of '0' =48) to change it to integer
	string cardNum;
	
	cout << "# This program uses the Luhn Algorigthm to validate a Card number. #" << endl;
    cout << "You can enter 'exit' anytime to quit." << endl;
    cout<<endl;
    
    
    while (true) {
        
        cout << "Please enter a Card number to validate: ";
        cin >> cardNum;
        
        if (cardNum == "exit")
            break;
            
        else if (!isstringnumber(cardNum)) {
            cout << "Invalid input! ";
            continue;
        }
        
        //step 1 
        //multiply of 2 with the every second digit from the right of the card number
        //if the product is in two digits, take the sum of them 
        //take the sum of above calculated values
		
		int len=cardNum.length();
		int doubleevensum=0;
		
		for(int i=len-2;i>=0;i=i-2)
		{
			int dbl=(cardNum[i]-48)*2;	
			if(dbl>9)
			{
				dbl=(dbl/10)+(dbl%10);
			}
			doubleevensum+=dbl;
		} 
		
		//step 2
		//take the sum of the remaining numbers
		
		int oddsum=0;
		
		for(int i=len-1;i>=0;i=i-2)
		{
			oddsum += (cardNum[i]-48);
		}
		
		//step3
		//take the sum of the above both results
		//check if it is the modulus of 10 to be considered as the VALID card number 
		
	int ultimate_sum=doubleevensum+oddsum;
    cout<< (ultimate_sum % 10==0 ? "The given card number is VALID" : "The given card number is INVALID");
    cout<<endl;
    continue;
	return 0;	
	}
}
