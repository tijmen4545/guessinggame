#!/usr/bin/ env bash
# File: guessingame.sh
 
echo "Welcome to guessinghame, guess how many files are in the current director>
 
response=0
files=$(ls | wc -l)
 
function getuserinput {
 echo "Please enter the number of files in the directory"
 read response
}
 
while [[ $response -ne $files ]]
do
  getuserinput
  if [[ $response -lt $files ]]
  then
  echo "$response is not correct, try to enter a higher number"
  elif [[ $response -gt $files ]]
  then
  echo "$response is not correct, try to enter a lower number"
  else
  echo "Something went wrong"
  fi
done

echo "You entered the correct number: $response, great job!"
