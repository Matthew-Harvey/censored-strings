# censored-strings
https://edabit.com/challenge/Wv9ZeXyC32EMfRWGB My solution in various languages to this problem.

C++:

std::string uncensor(std::string str, std::string vowels) {
	std::string res = "";
	int cur = 0;
	for(int i = 0; i < str.size(); i++) {
		if(str[i] == '*') {
			res += vowels[cur];
			cur++;
		}
		else {
			res+= str[i];
		}		
	}
	return res;
}

Python:

def uncensor(txt, vowels):
    listTxt = list(txt)
    listVowels = list(vowels)
    vowelsCounter = 0
    for x in range(len(listTxt)):
        if listTxt[x] == "*":
            listTxt[x] = listVowels[vowelsCounter]
            vowelsCounter += 1

    result = ""
    for x in listTxt:
        result += x
    
    return result

JavaScript:

function uncensor(str, vowels) {
	var newString = ''
	var vowelsCounter = 0
	for(var i = 0; i < str.length; i ++){
		if(str.charAt(i)==='*'){
			newString += vowels[vowelsCounter]
			vowelsCounter++
		}
		else{
			newString += str.charAt(i)
		}
	}
	return newString
}

Java:

public class Challenge {
	public static String uncensor(String str, String vowels) {
		String uncensored = "";
		int vowelCounter = 0;
		for (int i = 0; i < str.length(); i++) {
			uncensored += (str.charAt(i) != '*' ? str.charAt(i) : vowels.charAt(vowelCounter++));
		}
		return uncensored;
	}
}

