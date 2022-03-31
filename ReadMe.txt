Breakdown of Mole.bat

Batch files (.bat) may be considered antiquated in some circles, but they still work and are easy to pack as an executable. This is an update on a prank I used to pull when people were having fierce debates about LS120 vs 3.5"floppy (LS120 for life). In the "Way Back When" of which I speak the TIMEOUT command wasn't really a thing, so I would instead ping home (127.0.0.1) a *large* set interval of times to cause a pause as it had to wait for an acknowledgement, the TIMEOUT command not only addresses this but adds a layer of kindness to the prank as the prankee can keypress to stop the count (on the first instance).

@echo off - states that your filepath will not be continually displayed with output

:START - Flag for a GOTO call (kind of a big deal)

TIMEOUT - Inserts a pause in execution,  /T sets the pause interval declared in seconds, I set to 4 seconds to allow the prankee to read the message   !!CAUTION!! don't set this boundary too low

start mole.bat - executes the .bat…… again 

GOTO START - Who doesn't love a loop?

So you have a .bat big WOOP, what next? Simple, make it an executable. If you are a Windows user you already have an application to allow you to do this called IExpress in your system32.

1.Run IExpress and tell it to “Create new Self Extraction Directive file.” (Self extraction… see where we are going?)
 
2.Next you will want your package to “Extract files and run at installation command”, otherwise it will just unpack, not unpack and run. 

3.You can name your package whatever you like, and for this application we will not want a confirmation prompt (more fun this way).
  
4.We aren’t the type of folks that care about a license agreement, so skip that

5.IMPORTANT: Add> then select your batch file as your package file to … simple as that

6.We use command line to install the “program”, which is just cmd /c <filename>.bat

7.Set the place you want the file built with browse (you can lift the file out after… its just an exe) but this is where you name your exe file initially

8.Then click through the rest of the options until you can create your package. Where you specified in Step 7 now has your exe file.

So now you have a .exe file? But I have to be there to execute it or trick them into clicking on it… lame prank. Well hold on… we have two ways to address this.

1.Run (windows key + r) shell:startup and add a shortcut to your executable in said folder, will now execute on startup

2.Task Scheduler! (preferred method) Create a basic task where you select the time and day, or interval, to execute the program (you can set triggers too if you know your way around event IDs). Set the action to start your executable and sit back.

Select a time where you know the person will be using the computer…. We don’t want this going off forever, it is built to not be malicious but if it runs for an extended length of time the system may require a hard reboot… but that will take a LONG time with the 4 second interval.

