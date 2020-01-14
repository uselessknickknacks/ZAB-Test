# ZAB-Test
Zelda Automated Bowler for PC (aka for use on **cemu emulator**) made in Java. This is the first public test/tide me over version and automation is disabled. READ THE README! Windows 10 required!


While I work on finishing the rest of the dialogs (it can currently automate bowling and getting strikes + go trough dialog, but it cannot yet recover from a failed throw and it's associated dialogs), I figured I would release this to see if anyone wants to test it. So worth mentioning it again: Automation is disabled in this upload.
After you have tested the macros, open a issue if you found anything not working as expected, not getting a strike 100% of the time is to be expected and I will close any issues mentioning it. I want to know if link fails to throw the ball etc etc or presses a button sooner or later than he should, or if he presses a button for to long.

I'd say you should be getting strikes atleast 70-90% of the time, but I have no statistics to find out.

I also want to know if the program did not start as expected etc.
You will need Java 8 as I am compiling it against that one.

When I am finished with the dialogs and version 1.0 comes out. It will be fairly basic, it's currently heavily targetted towards my own specifications as a start. But for this specific test. All you need are the following:

*Game should be running at 720p, 1920x1080 for your desktop.. But the gamewindow itself need not be full screen (you cannot anyways since you have like 1-2 seconds after pressing one of the buttons to click with your mosue at the game windows atleast one time).
*You need the game locked at 30 fps and you also need it to be able to run constantly at 29.50-30 fps. 
*You need to be wearing the snow boots (the boots that let's you walk/run normally on snow)

Why I made it: For fun and exercise.
Why not just use AutoHotKey: Perhaps I could. But that would be no fun. I also do not know how it works.
This also uses tess4j (Tesseract OCR) to extract text from images as a way to handle decision making in dialogs. That's freaking cool. (Mostly because I know squat at all about memory reading and maths.

100 MB?!?!?!: Yhea, the traineddata for the latin letters for tesseract takes up lots of data, the english traineddata takes up it's fair space too. I had to pick the best one (which is bigger than the fast one) to lower the chances enough of getting a failed string reading from images.

How does that tesseract stuff work anyways?: Fuck if I know. In the source code I simply take a screenshot of your game (when it is in fullscreen, this is not applicable in this current test)'s dialog box down there at the bottom middle, when the ball has struck it's target. Then this bad boy engine reads that shit and extracts text into a string. Looking for unique words in what pondo says on that image, allows the application to know which way to go and what methos to trigger.

I am sharing this with you because I am nice.

**MIT License, I do not take any responsibility if this fries your computer.**

Instructions:

Go to pondos hut.

Grab the KeyboardMacroPondos.txt file and plop it into your cemu/controllerProfiles folder. Load that up as your controllerscheme.

Grab the jar from here: https://easyupload.io/4b9urd
Password is (without quotes "):  "pondoforeclosed"

Place the jar in it's own folder somewhere. Give the folder a cheeky name and a squeeze on the buttocks.

Go to pondo with the intention of getting him to foreclose because of all the rupees you will be robbing him off.
Pay him the enter fee and keep going trough dialog until you reach the point where you are in control again (After he says Good Luck).
Start the java application and place it above your game screen so you can quickly click on the game window.

The first time (when you spawn facing diagonally ish towards the pins) you click the "Debug: doFirstStrike" button and then quickly (and I mean quickly) click anywhere on the game screen with your left mouse button so it get's the focus.
Do not touch anything until after the ball has been thrown. The macro will position Link and aim (using the right foot on the stone, aim sensor at moose eye strategy).

If you got a strike. Great!
Go trough the dialog and pay him again etc when he says "Soooooo... What do you think about giving it one more whirl?".
When you get control again, you click the "Debug: doSubsequentStrike". And same as before, quickly click anywhere on the gamescreen.
Let it do it's thing and hope for yet another strike.

Every attempt where pondo has said "Soooooo... What do you think about giving it one more whirl?" you use "Debug: doSubsequentStrike" button.

Everytime you leave pondo (or have arrived at him) and he says "Halloooo kiddums", you use "Debug: doFirstStrike" the first time.


Ty for testing. :)
Do bring a barfing bag if you open the jar and peek at the sourcecode. It's a bit of a spaghettiville in there.
