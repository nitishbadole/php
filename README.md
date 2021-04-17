<?php

# DATE
echo "Data processed";

date_default_timezone_set('UTC');

echo date('h:i:s:u a, l F jS Y e');

# FORM POST (variables)
$usersName = $_POST['username'];
$streetAddress = $_POST['streetaddress'];
$cityAddress = $_POST['cityaddress'];

echo $usersName . "</br>";
echo $streetAddress . "</br>";
echo $cityAddress . "</br></br>";

# EOD String sytax
$str = <<<EOD
	The customers name is
	$usersName and they
	live at $streetAddress
	in $cityAddress</br>
EOD;

	echo $str;

# OPERATORS
	define('PI', 3.1415926);

	echo "The value of PI is " . PI;

	echo "</br>5 + 2 = " . (5 + 2);
	echo "</br>5 - 2 = " . (5 - 2);
	echo "</br>5 * 2 = " . (5 * 2);
	echo "</br>5 / 2 = " . (double)(5 / 2);
	echo "</br>5 % 2 = " . (5 % 2) . "</br>";

# INCREMENT
$randNum = 5;

echo $randNum += 10;
echo "</br>";

echo "++randNum = " . ++$randNum . "</br>";
echo "randNum++ = " . $randNum++ . "</br>";
echo $randNum;

# CASTING
$randNum = 5;
$refToNum = &$randNum;
$randNum = 100;

echo '$refToNum = ' . $refToNum;

# ARITHMETICS
if(5 == 10) {
	echo '5 = 10';
} else {
	echo '5 != 10';
}

$numOfOranges = 4;
$numOfBananas = 36;

// IF STATEMENTS
if ( ($numOfOranges > 25) && ($numOfBananas > 30) ) {
	echo '25% Discount';
} else if ( ($numOfOranges > 30) || ($numOfBananas > 35) ) {
	echo '15% Discount';
} else if ( !($numOfOranges < 5) || !($numOfBananas < 5) ) {
	echo '5% Discount';
} else {
	echo 'No Discount for you';
}

# TERNARY OPERATOR
$biggestNum = (15 > 10) ? 15 : 10;

echo $biggestNum;

# SWITCH STATMENT
switch ($usersName) {
	case "Derek" :
		echo "Hello Derek";
		break;

	case "Sally" :
		echo "Hello Sally";
		break;

	default :
		echo "Hello Valued Customer";
		break;
}

# LOOPS
	$num = 0;

	while($num < 20) {
		echo ++$num . ', ';
	}

	for($i = 1; $i <= 20; $i++) {
		echo $i;

		if($i != 20) {
			echo ', ';
		} else {
			break;
		}
	}

# ARRAYS
$bestFriends = array('Joy', 'Willow', 'Ivy');

//echo 'My Wife ' . $bestFriends[0];

$bestFriends[4] = 'Steve';

foreach ($bestFriends as $friend) {
	echo $friend . ', ';
}

$customer = array('Name'=>$usersName, 'Street'=>$streetAddress, 'City'=>$cityAddress);

echo "</br>";

foreach ($customer as $key => $value) {
	echo $key . ' : ' . $value . "</br>";
}

$bestFriends = $bestFriends + $customer;

# MULTI-DIMENSIONAL ARRAYS
$customers = array(array('Derek', '123 Main', '15212'),
				   array('Derek', '123 Main', '15212'),
				   array('Derek', '123 Main', '15212'));

for ($row=0; $row < 3; $row++) { 
	for ($col=0; $col < 3; $col++) { 
		echo $customers[$row][$col] . ', ';
	}
	echo '</br>';
}

// Common Array Functions
// sort($yourArray) : Sorts in ascending alphabetical order or
// if you add , SORT_NUMERIC or , SORT_STRING
// asort($yourArray) : sorts arrays with keys
// ksort($yourArray) : sorts by the key
// Put a r infront of the above to sort in reverse order

# STRING FUNCTIONS & FORMATTING
$randString = "			Random String 		";

echo strlen("$randString") . "</br>";
echo strlen(ltrim("$randString")) . "</br>";
echo strlen(rtrim("$randString")) . "</br>";
echo strlen(trim("$randString")) . "</br>";

# Conversion Codes (printf)
echo "The randomString is $randString </br>";
printf("The randomString is %s </br>", $randString);

$decimalNum = 2.3456;

printf("decimal num = %.2f </br>", $decimalNum);

// Other conversion codes
// b : integer to binary
// c : integer to character
// d : integer to decimal
// f : double to float
// o : integer to octal
// s : string to string
// x : integer to hexadecimal*/

$randString = "Random String";

echo strtoupper($randString) . "</br>";
echo strtolower($randString) . "</br>";
echo ucfirst($randString) . "</br>";

$arrayForString = explode(' ', $randString, 2);
$stringToArray = implode(' ', $arrayForString);
$partOfString = substr("Random String", 0, 6);

echo "</br>";

echo $partOfString;

echo "</br>";

$man = "Man";
$manhole = "Manhole";

echo strcmp($man, $manhole);
echo strcasecmp($man, $manhole);

echo "The String " . strstr($randString, "String");
echo "</br>";
echo "Loc the String " . strpos($randString, "String");
echo "</br>";

$newString = str_replace("String", "Stuff", $randString);
echo $newString;
echo "</br>";

# FUNCTION
function addNumbers($num1, $num2) {
	return $num1 + $num2;
}

echo "3 + 4 = " . addNumbers(3, 4);

?>
