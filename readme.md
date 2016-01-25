
---

| Title | Type | Duration | Name | City |
| --- | --- | --- | --- | --- |
| Activity Lifecycle | Lab | "1:00" | James Davis | NYC |

---  
# Activity Lifecycle Lab

## Introduction

Below, you will find three scenarios, and questions following each one.

To the best of your ability, answer the questions **in english**, not in code.

Below the scenarios, you will find a few questions. Answer those however you'd like.

Answer the questions by editing this readme, pushing your changes to your forked repo, and making a pull request.

## Exercise  


####Scenario 1:

Let’s say you made a To Do list app, where you can add things to a list and cross them off. You decide to cross some items off the list and mark them as complete.

When you rotate the device, the things you marked as complete are no longer crossed off.

**Question**: Why did this happen?
<br />Answer:
The activity is destroyed without saving . It then creates it again.

**Question**: How do you fix this issue?
<br />Answer:
You create a sharedPreferences of which saves the file to your phone when it pauses(onPause()). And then you call the sharedPreferences again onResume().


####Scenario 2:

The Amazon Kindle Android app allows you to open and read eBooks. You discovered a bug! You opened a book, and read it from the beginning up to page 68. Then, you left the app and closed it completely so you can do other things.

When you opened the app again, and opened the book, it started from page 1 (and not page 68 where you left off)!

**Question**: How would you fix this issue?
<br />**Answer**:

Create a sharedPreferences that saves the page number (save the int) when the onPause with is called, and displays the page number when the onResume is called (get that int number back).


OnSavedPreferences will hold it within the activity. Will not really save. SharedPreferences saves onto the phone and can be accessed anytime. 





####Scenario 3:

Facebook for Android added a feature last year where, if you started writing a comment on someone’s post and decided not to do so, the app would save a draft of it just in case you changed your mind.

Take this scenario. On a post on Facebook, you click the “comment” button (which opens a new CommentActivity). You start writing a comment, and then change your mind by pressing the back key (which closes the CommentActivity). You click on the “comment” button again, and in the newly-opened CommentActivity, the comment you were writing is still there.

**Question**: How would you implement this feature? Be specific; what lifecycle methods would you use in CommentActivity, and what techniques would you use?
<br />**Answer**:

on the onPause method, you do an EditText.getText().toString(); and you save that to an SharedPreferences. Then when the onResume(); is called, you can called the string and put it baack in with editText.setText():




In your own words…
==================

**Question**: What are the methods of the Activity Lifecycle?
<br />**Answer**: 
onCreate();
onStart();
onResume();

onPause();
onStop();
onDestroy();

**Question**: What order are the methods called?
<br />**Answer**: 
The order that I set them in above. 


**Question**: What is a bundle?
<br />**Answer**: 
A bundle is a thing with stuff in it. 
When you create a new intent you are creating a new bundle. 


**Question**: How do you get the Shared Preferences of an app?
<br />**Answer**:
If you are looking at context you can always get SharedPreferences.
SharedPreferences sharedpreferences = getSharedPreferences("com.simon.appname")
SharedPreferences.Editor editor = sharedPreferences.edit();
sharedpreferences.putString("Key", data);
editor.commit();


//Get data from Shared Preferences
sharedpreferences.getString("key","DEFAULT..or nothing Found")  ----- if you do not do a "DEFAULT", it will return null. 





