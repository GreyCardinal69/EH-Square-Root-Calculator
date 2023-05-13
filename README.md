# EH-Square-Root-Calculator
A square root calculator made with Event Horizon game quests.![Screenshot 2023-05-13 174910](https://github.com/GreyCardinal69/EH-Square-Root-Calculator/assets/50517794/d44b904d-c7be-46ee-a242-9607917e61a5)

To start the quest you need to take a faction mission from any faction.

The option "Clear Number To Calculate" sets the Number to calculate to 0.

![Screenshot 2023-05-13 174800](https://github.com/GreyCardinal69/EH-Square-Root-Calculator/assets/50517794/13956770-bdd5-43b8-9ba9-73fe8d2b30f1)
![Screenshot 2023-05-13 174843](https://github.com/GreyCardinal69/EH-Square-Root-Calculator/assets/50517794/7557373b-49fe-43cf-b8f0-3f0918b04e51)
![Screenshot 2023-05-13 174910](https://github.com/GreyCardinal69/EH-Square-Root-Calculator/assets/50517794/1ddf0993-1719-43f2-82ba-99e0af5efb90)

The following is the pseudo code of the calculator ( covers most of how it works. )

```cs
var substr = 0;
var remainder;

bool substr_larger;

remainder -= 1;
substr++;

while !substr_larger { // node 11
	var temp3;
	var temp4;

	while substr { // node 12
		substr--;
		temp3++;
	}

	while remainder { // node 15
		remainder--;
		temp4++;
	}

	while temp3 > 0 && temp4 > 0 { // node 19
		substr++;
		remainder++;
		temp3--;
		temp4--;
	}

	if temp3 > 0 && temp4 <= 0 { // node 24
		substr_larger = true;
	}

	while temp3 { // node 26
		temp3--;
		substr++;
	}

	while temp4  { // node 29
		temp4--;
		remainder++;
	}

	substr += 2; // node 32
	int temp;

	while substr > 0 { // node 33
		substr--;
		temp++;
		temp2++;
	}

	while temp > 0 { // node 37
		temp--;
		substr++;
	}

	while temp2 > 0 { // node 40
		temp2--;
		remainder--;
	}
}
....
