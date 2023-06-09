# EH-Square-Root-Calculator
A square root calculator made with Event Horizon game quests.

To start the quest you need to take a faction mission from any faction.

The option "Clear Number To Calculate" sets the Number to calculate to 0.

Since Quests support only whole numbers, the mantissa of the square root is not calculated.
For example the square root of 100.000 is 316.2277.... But it will show only 316.
Due to the constraints of the Quest system, slow game code and the simple lack of +, -, *, / and other basic operators, the calculator is quite slow.
For example to calculate the square root of 100.000 it requires 26 minutes on a high end laptop

The pre made Number to get the square root of is set at loot/Number To Calculate.json

![Screenshot 2023-05-13 174800](https://github.com/GreyCardinal69/EH-Square-Root-Calculator/assets/50517794/13956770-bdd5-43b8-9ba9-73fe8d2b30f1)
![Screenshot 2023-05-13 174843](https://github.com/GreyCardinal69/EH-Square-Root-Calculator/assets/50517794/7557373b-49fe-43cf-b8f0-3f0918b04e51)
![Screenshot 2023-05-13 174910](https://github.com/GreyCardinal69/EH-Square-Root-Calculator/assets/50517794/1ddf0993-1719-43f2-82ba-99e0af5efb90)

Some Examples:

![Screenshot 2023-05-13 152827](https://github.com/GreyCardinal69/EH-Square-Root-Calculator/assets/50517794/30be1830-b740-4b59-9301-126f31997e8c)
![Screenshot 2023-05-13 154226](https://github.com/GreyCardinal69/EH-Square-Root-Calculator/assets/50517794/02dda0ab-e837-4c99-b60a-b6f2569ae823)
![Screenshot 2023-05-13 162508](https://github.com/GreyCardinal69/EH-Square-Root-Calculator/assets/50517794/fd58f545-e0ec-42fd-a00d-08e232ec1c1c)


The following is the pseudo code of the calculator ( covers most of how it works. )

```cs
var substr = 0;
var remainder;

var temp1;
var temp2;
var temp3;
var temp4;

bool substr_larger;

remainder -= 1;
substr++;

while !substr_larger { // node 11

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
