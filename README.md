Start Length+Number_Button when green flag is pressed
	Hide
Start Button when green flag is pressed
	Switch costume to costume1
	Hide
Start Ball when green flag is pressed
	Hide
Start backdrop when green flag is pressed
Set all variables
Switch backdrop to Slide_1_Intro
Play sounds until done
Wait until space key is pressed
If space key is pressed then
		Switch backdrop to Slide_2
		Stop all sounds
		Forever
If variable Touch_Number is not equal to 0 and variable Number is not equal to 0 and variable Touch_Length is not equal to 0 and variable Length is not equal to 0 then
			Switch backdrop to Length+Number_Suri+Juana
				Start sprite Length+Number_Button
					Switch costume to costume2
					Reset position
					Forever
						If mouse-pointer touches it then
							Set size to 120%
							Switch costume to costume1
							Change variable Touch_Length by 1
							Change variable Touch_Number by 1
							Wait 0.5 seconds
							Hide
						Else
							Set size to 100%
							Switch costume to costume2						
			Play sound Length_Suri until done
			Ask “How long do you want your password to be?” and wait
			Set answer to variable Length
					Play sound Number_Juana until done
					Ask “Choose a number.” and wait
					Set answer to variable Number
					Broadcast message1
					Stop this script

Start sprite Button when message1 is broadcasted
	Show
	Wait until the mouse pointer touches it
	Switch costume to costume2
	Wait 0.25 seconds
	Broadcast message2
	Hide
	Stop this script
Start backdrop when message2 is broadcasted
	Switch backdrop to Suri_Purpose
	Play sound Purpose_Suri
	Ask “So, where will this password be used and what is this place’s purpose?” and wait
	Set answer to variable Sentence
	Broadcast message3
	Stop this script
Start backdrop when message3 is broadcasted
	Switch backdrop to Stop_Juana+Suri
	Start sounds
	Wait variable Length/2 seconds
	Switch backdrop to Info+Password_Suri+Juana
	Play sounds until done
Start sprite Ball when message3 is broadcasted
	Wait variable Length/2 seconds
	Show
	If variable Sentence contains a (space) then
		Set variable Letter to 1 of variable Sentence
		Set variable Letter to 5 of variable Sentence
		Set variable Letter to 9 of variable Sentence
		Set variable Letter to 13 of variable Sentence
		Set variable Letter to 17 of variable Sentence
		Set variable Letter to 21 of variable Sentence
		Set variable Letter to 25 of variable Sentence
		Set variable Letter to 29 of variable Sentence
Else
	Set variable Letter to 1 of variable Sentence
	Set variable Letter to 4 of variable Sentence
	Set variable Letter to 8 of variable Sentence
	Set variable Letter to 12 of variable Sentence
	Set variable Letter to 16 of variable Sentence
	Set variable Letter to 20 of variable Sentence
	Set variable Letter to 24 of variable Sentence
	Set variable Letter to 28 of variable Sentence
Set variable Password to variable Letter + variable Letter_2 + variable Letter_3 + variable Letter_4 + variable Letter_5 + variable Letter_6 + variable Letter_7 + variable Letter_8 + variable Number
Repeat until length of variable Password is equal to variable Length
	If length of variable Password is equal to variable Length then
		Say variable Password
	Else
		If length of variable Password is more than variable Length then
			Repeat until length of variable Password is equal to variable Length
				Set variable Password to variable Password – letter 1 of variable Password
		Else
			Repeat until length of variable Password is equal to variable Length
				Set variable Password to variable Password + variable Number
	Say variable Password
