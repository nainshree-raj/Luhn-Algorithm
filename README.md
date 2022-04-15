# Luhn-Algorithm or modulus-10
Checksum Validation Algorithm

Luhn Algorithm is a simplechecksum formula used to validate different identification numbers like
# Credit Card Numbers, IMEI(International Mobile Equipment Identity) Numbers, National Provider Identifier Numbers,etc. 

What is checksum?
Answer : It is a small size calculated data from a input for the purpose of detecting error transmission or storage.

# Steps to be followed :
16 digits credit card number -

1)Drop the last digit from the card number. The last digit (16th position) is called Luhn key.
2)Evaluate each digit from right to left. When the digit is in odd positions, we multiply it by 2.
3)Add all the numbers together.
4)Compute the Luhn Key. This (last) digit is the amount that you would need to add to the previous total (computed above in step 3) to get a multiple of 10 (Modulo 10). This Luhn key has to be equal to the last digit which has been removed in step 1.

Hence, if Luhn Key is equal to the calculated last digit by these steps, then it is considered to be a VALID credit card number.

# Major Industry Identifier (MII) - in the attached photo.
The first digit of the credit/debit card is the Major Industry Identifier (MII). It indicates the category of the entity which issued the card.
* 1 and 2: Airlines
* 3: Travel and Entertainment
* 4 and 5: Banking and Financial Services
* 6: Merchandising and Banking
* 7: Petroleum
* 8: Health care, Telecommunications
* 9: National Assignment

# Issuer Identification Number (IIN) - in the attached photo.
The first six digits are the Issuer Identification Number (IIN). These denotes the institution that issued the card.
For example, Visa cards begin with a 4, while MasterCard ones start with number between 51 and 55.

The first fifteen digits are determined by the issuing bank, 
# but the last digit, called the *check digit*, is mathematically determined based on all other digits,using Luhn Algorithm.
