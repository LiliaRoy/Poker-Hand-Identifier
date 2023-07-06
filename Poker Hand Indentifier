//the cards the player has in hand + community pile
const prompt = require('prompt-sync')();

var valid = true;

var card1;
var card2;
var card3;
var card4;
var card5;
var card6;
var card7;

//function to ask for the cards
getCards();

///the cards (the list) is equal to the cards (the strings) for the entire program
const cards = [card1, card2, card3, card4, card5, card6, card7];
//creates an array for cardSuits
const cardSuits = [];

for (let i = 0; i < cards.length; i++) {
  if (cards[i][1] == "0") {
    cardSuits.push(cards[i][2]);
  }
  else {
    cardSuits.push(cards[i][1]);
  }
}

console.log(cardSuits);

for (let i = 0; i < cards.length; i++) {
  //evaluates first character of all the strings to determine ace, king, 10, etc
  if (cards[i].at(0) == 'J') {
    //changes first character of string to 1
    var string1 = cards[i].replace("J", "1");
    //stores the suit
    var temp = cards[i].charAt(1);
    //changes it to an 11
    var string2 = string1.replace(temp, "1");
    //adds the suit back in
    var string3 = string2.concat(temp);
    cards[i] = string3;
  }
  //same for the rest, except different cards
  else if (cards[i].at(0) == 'Q') {
    //changes first character of string to 1
    var string1 = cards[i].replace("Q", "1");
    //stores the suit
    var temp = cards[i].charAt(1);
    //changes it to an 11
    var string2 = string1.replace(temp, "2");
    //adds the suit back in
    var string3 = string2.concat(temp)
    cards[i] = string3;
  }
  else if (cards[i].at(0) == 'K') {
    //changes first character of string to 1
    var string1 = cards[i].replace("K", "1");
    //stores the suit
    var temp = cards[i].charAt(1);
    //changes it to an 11
    var string2 = string1.replace(temp, "3");
    //adds the suit back in
    var string3 = string2.concat(temp)
    cards[i] = string3;
  }
  else if (cards[i].at(0) == 'A') {
    //changes first character of string to 1
    var string1 = cards[i].replace("A", "1");
    //stores the suit
    var temp = cards[i].charAt(1);
    //changes it to an 11
    var string2 = string1.replace(temp, "4");
    //adds the suit back in
    var string3 = string2.concat(temp)
    cards[i] = string3;
  }
}

const cardValues = [parseInt(cards[0]), parseInt(cards[1]), parseInt(cards[2]), parseInt(cards[3]), parseInt(cards[4]), parseInt(cards[5]), parseInt(cards[6])];


//set the variables for all types of hands to false in the beginning
var flush = false;
var straight = false;
var straightFlush = false;
var royalFlush = false;
var pair = false;
var twoPair = false;
var threeKind = false;
var fourKind = false;
var fullHouse = false;

//points variable
let points = 0;

//establishes that the list of cards is equal to the cards for the entire program

//functions for types of hands
flushPossible();
straightPossible();
pairsPossible();

//calls functions that check for types of hands
if(flush==true&&straight==true){
  straightFlushPossible();
}
if (straightFlush==true){
  royalFlushPossible();
}


if (valid == true) {
  if (royalFlush==true){
    console.log("Royal Flush!");
    var bestHand = "Royal Flush";
  } else if (straightFlush==true){
    console.log("Straight Flush!");
    bestHand = "Straight Flush";
  } else if (fourKind==true){
    console.log("Four of a kind!");
    bestHand = "Four of a Kind";
  } else if (fullHouse==true) {
    console.log("Full House!");
    bestHand = "Full House";
  } else if (flush==true) {
    console.log("Flush!");
    bestHand = "Flush";
  } else if (straight==true) {
    console.log("Straight!");
    bestHand = "Straight";
  } else if (threeKind==true) {
    console.log("Three of a Kind!");
    bestHand = "Three of a Kind";
  } else if (twoPair==true){
    console.log("Two Pair!");
    bestHand = "Two Pair";
  } else if (pair==true) {
    console.log("Pair!");
    bestHand = "Pair";
  } else {
    console.log("High Card!");
    bestHand = "High Card";
  }
}

//evaluates the suits for royal flush
//royal flush function
function royalFlushPossible(){
  if (cards.includes("14S") && cards.includes("13S") && cards.includes("12S") && cards.includes("11S") && cards.includes("10S")) {
    royalFlush = true;
  }
  else if (cards.includes("14H") && cards.includes("13H") && cards.includes("12H") && cards.includes("11H") && cards.includes("10H")) {
    royalFlush = true;
  }
  else if (cards.includes("14D") && cards.includes("13D") && cards.includes("12D") && cards.includes("11D") && cards.includes("10D")) {
    royalFlush = true;
  }
  else if (cards.includes("14C") && cards.includes("13C") && cards.includes("12C") && cards.includes("11C") && cards.includes("10C")) {
    royalFlush = true;
  }
  else {
    royalFlush = false;
  }
  //checks to see if you have all of each suit, returns true if so
}
function pairsPossible(){
  for (var x = 0;x<cardValues.length;x++){
    var valueX = cardValues[x];
    const xValues = cardValues.filter((value) => value == valueX);
    var frequency = xValues.length;
    if(frequency == 4){
    fourKind = true;
    } else if (frequency==3&&threeKind==true){
      fullHouse = true;
    } else if (frequency==3){
      threeKind=true;
    } else if(frequency==2&&pair==true){
      twoPair=true;
      var curentTwoPair=true;
    } else if (frequency==2){
      pair = true;
      var currentPair = true;
    }
    if(pair==true&&(threeKind==true||fourKind==true)){
      fullHouse = true;
    }
  }
}

//if (cardValues.includes(cardValues[i] + 1) && cardValues.includes(cardValues[i] + 2) && cardValues.includes(cardValues[i] + 3) && cards.includes(cardValues[i] + 4))
//evaluates the highest-ranking pair found for points
//function pointsProcessor() {
  if (bestHand = royalFlush){
    pointPossible = 0;
    //I just put 0 here so it doesn't show up as incomplete to the computer
  }

//straight flush function

function straightFlushPossible() {  
  for (var i = 0; i < cardValues.length; i++) {
    if (cardValues.includes(cardValues[i] + 1) && cardValues.includes(cardValues[i] + 2) && cardValues.includes(cardValues[i] + 3) && cards.includes(cardValues[i] + 4)) {
      let index1 = cardValues.indexOf(cardValues[i] + 1);
      let index2 = cardValues.indexOf(cardValues[i] + 2);
      let index3 = cardValues.indexOf(cardValues[i] + 3);
      let index4 = cardValues.indexOf(cardValues[i] + 4);
      
      if (cardSuits[i] == cardSuits[index1] && cardSuits[index1] == cardSuits[index2] && cardSuits[index2] == cardSuits[index3] && cardSuits[index3] == cardSuits[index4]){
        straightFlush = true;
      }
    } else if (cardValues.includes(cardValues[i] - 1) && cardValues.includes(cardValues[i] - 2) && cardValues.includes(cardValues[i] - 3) && cardValues.includes(cardValues[i] - 4)) {
      let index1 = cardValues.indexOf(cardValues[i] - 1);
      let index2 = cardValues.indexOf(cardValues[i] - 2);
      let index3 = cardValues.indexOf(cardValues[i] - 3);
      let index4 = cardValues.indexOf(cardValues[i] - 4);
      
      if (cardSuits[i] == cardSuits[index1] && cardSuits[index1] == cardSuits[index2] && cardSuits[index2] == cardSuits[index3] && cardSuits[index3] == cardSuits[index4]){
        straightFlush = true;
      }
    }
  }

  if (cardValues.includes(14) && cardValues.includes(2) && cardValues.includes(3) && cardValues.includes(4) && cardValues.includes(5)) {
    let index = cardValues.indexOf(14)
    let index1 = cardValues.indexOf(2);
    let index2 = cardValues.indexOf(3);
    let index3 = cardValues.indexOf(4);
    let index4 = cardValues.indexOf(5);
      
    if (cardSuits[index] == cardSuits[index1] && cardSuits[index1] == cardSuits[index2] && cardSuits[index2] == cardSuits[index3] && cardSuits[index3] == cardSuits[index4]){
      straightFlush = true;
    }
  }
}

//four of a kind function
/*function fourKindPossible() {
  for (var x = 0;x<suits.length;x++){
    const copyValues = values.slice();
    var valueX = values[x];
    copyValues.splice(x, 1);
    var count = 1;
    for (var k = 0; k<3;k++){
      if(copyValues.includes(valueX)){
        var index = copyValues.indexOf(valueX);
        copyValues.splice(index,1);
        count++;
      }
    }
    if(count>=4){
      fourKind = true;
    }
  }
}*/

//function for three of a kind, not currently needed because threeKind is automatically checked for in pairsPossible();
/*function threeKindPossible(){
  for (var x = 0;x<suits.length;x++){
    const copyValues = values.slice();
    var valueX = values[x];
    copyValues.splice(x, 1);
    var count = 1;
    for (var k = 0; k<2;k++){
      if(copyValues.includes(valueX)){
        var index = copyValues.indexOf(valueX);
        copyValues.splice(index,1);
        count++;
      }
    }
    if(count>=3){
      threeKind = true;
    }
  }
}*/

//flush function
function flushPossible() {
  var H = 0;
  var C = 0;
  var D = 0;
  var S = 0;
  flush = false;

  //if includes, then repeat for = to crd lngth (not value, cause value is twice and changing)
  for (var i = 0; i < cardSuits.length; i++){
    if (cardSuits[i] == "H"){
      H++;
    } else if (cardSuits[i] == "C") {
      C++;
    } else if (cardSuits[i] == "D") {
      D++;
    } else if (cardSuits[i] == "S") {
      S++;
    } else {
      console.log("Not a valid suit.")
        valid = false;
    }
  }
  //checks to see if you have 5 of any suit
  if (H>=5||C>=5||D>=5||S>=5){
    flush = true;
  }
}

//straight function
//cards[i] + num doesn't work, because cards elements are strings. first remove suits and change into numbers

var straight;

//checks to see if a straight is possible
function straightPossible(){
  //originally sets boolean to false
  straight = false;
  //checks to see if it was a certain amount added to the given, or subtracted from the given
  for (var i = 0; i<cardValues.length; i++) {
    if (cardValues.includes(cardValues[i] + 1) && cardValues.includes(cardValues[i] + 2) && cardValues.includes(cardValues[i] + 3) && cards.includes(cardValues[i] + 4)) {
      //declares straight as possible if so
      straight = true;
    } else if (cardValues.includes(cardValues[i] - 1) && cardValues.includes(cardValues[i] - 2) && cardValues.includes(cardValues[i] - 3) && cardValues.includes(cardValues[i] - 4)) {
      straight = true;
    } else if (cardValues.includes(14) && cardValues.includes(2) && cardValues.includes(3) && cardValues.includes(4) && cardValues.includes(5)) {
      straight = true;
    } else {
      straight = false;
    }
  }
}

//include function! search if array includes a certain value!!
//sort function, ascending descending order, .sort
//function 
//card1Suit == card2Suit && card2Suit == card3Suit && card3Suit==card4Suit&&card4Suit==card5Suit&&card6Suit==card7Suit

//make suits and values from include function on for loop on the 5S cards array

//gets the cards
  
function getCards(){
  console.log("Card Value and Card Suit, no spaces. Example: '5S' or 'AC'. We will ask for all 7 cards.");
  card1 = prompt();
  console.log("Card Value and Card Suit, no spaces. Example: '5S' or 'AC'.");
  card2 = prompt();
  console.log("Card Value and Card Suit, no spaces. Example: '5S' or 'AC'.");
  card3 = prompt();
  console.log("Card Value and Card Suit, no spaces. Example: '5S' or 'AC'.");
  card4 = prompt();
  console.log("Card Value and Card Suit, no spaces. Example: '5S' or 'AC'.");
  card5 = prompt();
  console.log("Card Value and Card Suit, no spaces. Example: '5S' or 'AC'.");
  card6 = prompt();
  console.log("Card Value and Card Suit, no spaces. Example: '5S' or 'AC'.");
  card7 = prompt();
}
