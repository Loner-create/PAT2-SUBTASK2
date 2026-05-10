# PAT2-SUBTASK2
#include <iostream>
#include <map>
#include <string>
#include <cctype>
#include <vector>

std::map<char, std::string> morseCodeMap = {
    {'A', ".-"}, {'B', "-..."}, {'C', "-.-."}, {'D', "-.."},
    {'E', "."}, {'F', "..-."}, {'G', "--."}, {'H', "...."},
    {'I', ".."}, {'J', ".---"}, {'K', "-.-"}, {'L', ".-.."},
    {'M', "--"}, {'N', "-."}, {'O', "---"}, {'P', ".--."},
    {'Q', "--.-"}, {'R', ".-."}, {'S', "..."}, {'T', "-"},
    {'U', "..-"}, {'V', "...-"}, {'W', ".--"}, {'X', "-..-"},
    {'Y', "-.--"}, {'Z', "--.."}
};

std::vector<std::pair<char, std::string>> encodeToMorseCode(const std::string& text) {
    std::vector<std::pair<char, std::string>> morseCodeLetters;
    for (char c : text) {
       
        c = toupper(c);
        if (morseCodeMap.find(c) != morseCodeMap.end()) {
            morseCodeLetters.push_back(std::make_pair(c, morseCodeMap[c]));
        }
  }
    return morseCodeLetters;
}

int main() {
    std::string inputText;
    std::cout << "Enter a text to convert to Morse code:" ;
    std::getline(std::cin, inputText);

    std::vector<std::pair<char, std::string>> morseCodeLetters = encodeToMorseCode(inputText);
    for (const auto& pair : morseCodeLetters) {
        std::cout << pair.first << " : " << pair.second << std::endl;
    }

    return 0;
}
