#Hard drives are such bastards.

It's *hard* to take the eject messages seriously since 99.9% of the time everything is fine. But sometimes it goes wrong. ***REALLY*** wrong. Sometimes all you want to do is start over, but the wussy osx shitty macbook won't let you.

This is a last resort little script that completely fecks up a hard drive by attempting to randomly write over it. However the idea is that it "unsticks" the hard drive. Then you can start again from some sort of diskutil thing.

**Be fucking careful which disk you attack!** By default the script *"attacks"* `dev/disk2`. You should already know which one is causing the problems. Use `diskutil list` just to be sure.


##Running

 1. `cd` to the download directory and run the following command to make the script executable:

 `chmod 777 deep.sh`

 2. Now switch to root in the Terminal

 `sudo su`

 3. And finally run the script, immediately followed by attaching your drive to the Mac:

 `./deep.sh`

 4. Plug in the hard drive.

 5. Wait for the script to stop for a bit, then close the terminal and terminate processes.
