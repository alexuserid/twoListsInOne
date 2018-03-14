package main

import (
	"fmt"
	"io/ioutil"
	"log"
	"regexp"
)

func wordSlMaker(filename string) ([]string, error) {
	re := regexp.MustCompile(".+")
	bytes, err := ioutil.ReadFile(filename)
	if err != nil {
		return nil, err
	}
	return (re.FindAllString(string(bytes), -1)), nil
}

func main() {

	enWordSl, err := wordSlMaker("enWords.txt")
	if err != nil {
		log.Fatalf("Making enWordSl: %v", err)
	}
	ruWordSl, err := wordSlMaker("ruWords.txt")
	if err != nil {
		log.Fatalf("Making ruWordSl: %v", err)
	}

	dicSl := []string{}

	for i := range enWordSl { //range through enWordSl
		dicSl = append(dicSl, enWordSl[i]+" - "+ruWordSl[i]+"\n")
	}

	fmt.Println(dicSl)
}

//enWords.txt and ruWords.txt include list of words formed like:
//word1\n
//word2\n
//word3\n



//to avoid repiting in main() you can use another code, just replace main function by following code:
/*
func dicMaker(files ...string) ([]string, []string, error) {
	var enWordSl, rusWordSl []string
	for i := range files {
		wordSl, err := wordSlMaker(files[i])
		if err != nil {
			return nil, nil, err
		}
		if i == 0 {
			enWordSl = wordSl
		}
		rusWordSl = wordSl
	}
	return enWordSl, rusWordSl, nil
}

func main() {
	enWordSl, rusWordSl, err := dicMaker("enWords.txt", "ruWords.txt")
	if err != nil {
		log.Fatalf("dicMaker: %v", err)
	}

	dicSl := []string{}

	for i := range enWordSl {
		dicSl = append(dicSl, enWordSl[i] + " - " + rusWordSl[i] + "\n")
	}

	fmt.Println(dicSl)
}
*/
//but using of the code make all code more complicate and difficult to understand
