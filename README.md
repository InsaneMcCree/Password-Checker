# Password-Checker
C++ first project using basics functions. If, bools, variables, break, incrementing, for loops

#include <iostream>
#include <string>

std::string password;
int score = 0;
bool hasnumber = false;
bool hasspecial = false;

int main() {
  std::cout<<"===================\n";
  std::cout<<"Password Checker 🔐\n";
  std::cout<<"===================\n\n";

  std::cout<<"Enter your password: "; 
  std::cin>>password; //input

  if (password.length() >= 8) {
    ++score;
  }
  else{
    std::cout<<"❌ Password must be at least 8 characters.";
    return 0;
  }

  for (int i =0; password.length()>i; ++i){
    if (password[i] == '1' || password[i] == '2' || password[i] == '3' || password[i] == '4'|| password[i] == '5'|| password[i] == '6'|| password[i] == '7'|| password[i] == '8' || password[i] == '9' || password[i] == '0'){
      ++score;
      hasnumber = true;
      break;
    }
  }
  if (hasnumber == false){
    std::cout<<"❌ Password must include a number.";
    return 0;
}


for (int i =0; password.length()>=i; ++i){
  if (password[i] == '!' || password[i] == '@' || password[i] == '#' || password[i] == '%' || password[i] == '^'){
  ++score;
  hasspecial = true;
  break;
  }
}

if (hasspecial == false){
  std::cout<<"❌ Password must include a special character.";
  return 0;
}

if (score ==3) {
  std::cout<<"✅ Valid password!";
  return 0;
  }
}
