//Image Source:
//the state flag and map images were provided by code.org.

//salute-veterans-day.gif - https://www.google.com/url?sa=i&url=https%3A%2F%2Ftenor.com%2Fsearch%2Famerican-salute-gifs&psig=AOvVaw2p6IOtgs77SpthZWoGs6eY&ust=1713293920564000&source=images&cd=vfe&opi=89978449&ved=0CA8QjRxqFwoTCPDIkq3zxIUDFQAAAAAdAAAAABAE. 

//1f929.png - https://www.google.com/url?sa=i&url=https%3A%2F%2Femojiterra.com%2Fstar-struck%2F&psig=AOvVaw0pi5crfRkRoqSAYkpWNZL-&ust=1713293887965000&source=images&cd=vfe&opi=89978449&ved=0CBAQjRxqFwoTCNjTu5_zxIUDFQAAAAAdAAAAABAI. 

//ccfda11c-0382-43e4-9cca-fa76fadc8f2b-160x160.png - https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.iemoji.com%2Fview%2Femoji%2F1856%2Fsmileys-people%2Fhugging-face&psig=AOvVaw10dlkkP326deLu-6mV4Q48&ust=1713293824171000&source=images&cd=vfe&opi=89978449&ved=0CBAQjRxqFwoTCIjtsYLzxIUDFQAAAAAdAAAAABAD. 

//102738-gradient-great-job-emoji-download-hd.png - https://www.google.com/url?sa=i&url=https%3A%2F%2Ffreepngimg.com%2Fpng%2F102738-gradient-great-job-emoji-download-hd&psig=AOvVaw3iXSr4qSFWxclHKrvTmBYl&ust=1713293698058000&source=images&cd=vfe&opi=89978449&ved=0CBAQjRxqFwoTCPDx78TyxIUDFQAAAAAdAAAAABAD. 

//suspecting-emoticon-design-30573285-removebg-preview.png- https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.istockphoto.com%2Fphotos%2Fsuspicious-emoji&psig=AOvVaw3EkN4xMMIiolTja3S0d5wY&ust=1713293665609000&source=images&cd=vfe&opi=89978449&ved=0CBAQjRxqFwoTCPDwzLTyxIUDFQAAAAAdAAAAABAD.

//1916531-american-abstract-background-flag.jpg - https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.123rf.com%2Fclipart-vector%2Famerican_background_field.html%3Fsti%3Dmzgv5vn20f7geosb7j%257C&psig=AOvVaw3cJtTKYqGrAomGCWmHRkbl&ust=1713465130094000&source=images&cd=vfe&opi=89978449&ved=0CBAQjRxqFwoTCMCN-5XxyYUDFQAAAAAdAAAAABAD


//the lists are initiated
var state_Names = getColumn("US States", "State Name");
var maps_List = getColumn("US States","Map");
var flags_List = getColumn("US States","State Flag");

//The variables that check the score of the user, and how many guess the user has made are initiated.
var count = 0;
var score = 0;

//the code segment to give functionality to the button that takes the user to option screen,
onEvent("start_Button", "click", function( ) {
  setScreen("optionScreen");
});



//the code segment to give functioinality to the button that takes the user to quiz screen
onEvent("maps_Option_button", "click", function( ) {
  quizScreen(maps_List);
});
onEvent("flags_Options_Button", "click", function( ) {
  quizScreen(flags_List);
});


//This button will check if the option the user chose is correct or not.
onEvent("Check_Button", "click", function( ) {
  count = count + 1;
  scoring(checkAnswer(getImageURL("quiz_Images"),getText("Options_dropdown")));
  randomImage(getImageURL("quiz_Images"));
  result(score);
  


  //If the user has guessed 10 maps or flags then it will take the user to result screen.
  if (count == 10) {
    setScreen("result_Screen");
  }
});


//This button will allow the user to take the quiz again, and will also reset the score and the number of guesses the user made.
onEvent("Again_Button", "click", function( ) {
  score = 0;
  count = 0;
  setScreen("optionScreen");
  setText("check_Answer", "All The Best!!!");
});



//the procedure that has the code for option screen buttons to work.
//If the user choses maps quiz, then it will produce a random image from the list that holds the urls of maps.
//If the user choses flags quiz, then it will produce a random image from the list that holds the urls of flags.

function quizScreen(list) {
  setScreen("quiz_Screen");
  setProperty("Options_dropdown", "options", state_Names);
  setProperty("quiz_Images", "image", list[randomNumber(0,15)]);
}



//This procedure has the code that gives functionality to the check button.
//The states_traversal will traverse the entire names of states, and the flags_traversal and maps_traversal will traverse the traverse the maps and flags list.
//Once the url of the quizImage matches one of the list elements of maps or flags list, the collector variable will store the name of the state of that map or flag.
//Then, if the option that the user chose matches collector variable, then it will return true, otherwise it will return false. 

function checkAnswer(quizImage,userChoice) {
  var collector;
  var reviewer;
  for (var i = 0; i < state_Names.length - 1; i++) {
    var states_traversal = state_Names[i];
    var maps_traversal = maps_List[i];
    var flags_traversal = flags_List[i];
    if (quizImage == maps_traversal || quizImage == flags_traversal) {
      collector = states_traversal;
      if (userChoice == collector) {
        reviewer = "true";
      } else {
        reviewer = "false";
      }
    }
  }
  return reviewer;
}




//This procedure has that gives the quizImage a random image each time the user clicks the check button to make sure if he is correct or incorrect.
//If the current url of the quizImage matches one of the elements from maps_List that this procedure will produce a random image from the maps_List.
//If the current url of the quizImage matches one of the elements from flags_List that this procedure will produce a random image from the flags_List.

function randomImage(url) {
  for (var i = 0; i < flags_List.length-1; i++) {
    var flag_checker = flags_List[i];
    var map_checker = maps_List[i];
    if (flag_checker == url) {
      setProperty("quiz_Images", "image", flags_List[randomNumber(0,flags_List.length-1)]);
    } else if (map_checker == url) {
      setProperty("quiz_Images", "image", maps_List[randomNumber(0,maps_List.length-1)]);
    }
  }
}


//If the value that is returned from checkAnswer function is true, then it will increase user's score by 1, and it will also show that the user's answer is correct.
//If the value that is returned from checkanswer is not true then it will show the that user's guess is incorrect.
//It will also return the updated score each time.
function scoring(value) {
  if (value == "true") {
    score = score + 1;
    setProperty("check_Answer", "text", "CORRECT!");
  } else {
    setProperty("check_Answer", "text", "INCORRECT!");
  }
  return score;
}



//This precedure gives a output or response from the computer based on his score.
function result(tally) {
  if (tally == 10) {
    setProperty("output_Image", "image", "1f929.png");
    setProperty("endResults", "text", (tally+ "/10") + "\n Wondeful. You are basically a master at Geography and knowledge");
  } else if ((tally > 7)) {
    setProperty("output_Image", "image", "102738-gradient-great-job-emoji-download-hd.png");
    setProperty("endResults", "text", (tally + "/10") + "\n Damn. You are really good at this.");
  } else if ((tally > 3)) {
    setProperty("output_Image", "image", "suspecting-emoticon-design-30573285-removebg-preview.png");
    setProperty("endResults", "text", (tally + "/10") + "\n Take a few more test. Maybe, you'll score higher.");
  } else {
    setProperty("output_Image", "image", "ccfda11c-0382-43e4-9cca-fa76fadc8f2b_160x160.png");
    setProperty("endResults", "text", (tally + "/10") + "\n Don't Worry. We can learn and try again.");
  }
}


