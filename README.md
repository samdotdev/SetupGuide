Hello fellow coder :)
Here you will learn how to setup HGLabors's Kitapi and FFA. First make sure that you have: Java 11 or higher a working IDE such as Intellij

# SERVER SETUP
First you'll need a test server to test your kits/ffa. For that you will need The
Paper-Spigot (1.16.5) Then you will need create a
Folder on your Desktop (call it whatever you want) and drag the paper.jar into the
Folder. Make sure too actually call the .jar paper.jar. Next you need to create a
start.txt file in there you will paste the following text:
java -Xmx1G -jar paper.jar PAUSE
Now save the File as a .bat (File -> save under -> SERVERFOLDER. call it start.bat and
Data type should be: All types). Run the start.bat:
you will see that you have to accept the eula. You can find the eula.txt file in
your server folder, read it and change eula=false to eula=true. save it, stop
the server and run the server again. as you can see there should now be files
generated in your Server folder. You can also join the server now:
Start Minecraft go to add server and the server address is going to be localhost You
can now join the server.

NOTE: If there is any problem with running the start.bat, so you will get a paper error this CAN be the fault of your antivirus disable it to check if it works without it
DOWNLOADING PLUGINS
Download this files from the Web and drag them into your plugins folder located in your Server Folder
AsyncWorldEdit
LibsDisguises
ProtocolLib
WorldEdit

Restart your server, and you should see that many folders have been created in your Plugins Folder.

FFA AND KITAPI SETUP
Open these two sites:
KitAPi
FFA
Fork these two repos so:

press the Fork button on the top right.
go to your GitHub Profile and locate your repositories.

You will see that you have 2 repositories:
FFA and KitApi.
Clone both of them to your local machine. For that you need to have
Git installed,
Now: go to your Workspace and open up any kind of a Cmd and type:
git clone https://github.com/YOURNAME/HGLaborFFA2.0.git`<br>git clone https://github.com/YOURNAME/HGLaborKitAPI2.0`

Make sure to actually change YOURNAME to your github name.
INSTALLING BUILDTOOLS
Create a Folder on any of your drivers except for C and call it BuildTools.
Download BuildTools
Drag the .jar into your BuildTools folder.
Open up any kind of Cmd and Type: java -jar BuildTools.jar --rev 1.16.5

This is going to take a while do NOT close the command line while Buildtools is
installing!
If buildtools is finished check your Maven local so: C:\Users\YOURNAME.m2\repository\org\bukkit\craftbukkit
If this Folder is not there you will need to locate your BuildTools folder again open any
kind of a Cmd and type:
java -jar BuildTools.jar --rev 1.16.5 --compile craftbukkit
Now there should be a CraftBukkit folder.
COMPILING KITAPI
Note: You will need to do this every time you change something in the KitApi Code! Locate you KitApi folder, go inside it and open up cmd or git bash and type:
./gradlew generatePomFileForMavenPublication
then
./gradlew publishMavenPublicationToMavenLocal
then
./gradlew publishToMavenLocal
LAST STEP
Open Your Coding Environment (Intellij recommended) And open both projects so: KitApi & FFA.
I would also recommend opening The projects in separate windows, so:
File -> Open -> Select KitApi or FFa Folder -> OK -> New Window
Go into your FFA project and navigate to the main class (FFA) navigate to line 45 and
look for the String called SHARED_SERVER_DATA change the string to something like this:
C:\Users\Maquzo\Desktop\Server 1.16.5\plugins\HGLaborFFA2.0 So: Serverlocation -> plugins -> HGLaborFFA2.0 NOTE: If there is no HGLaborFFA2.0 Folder look at two steps under me and do this building step first. You will get an error but simply do this step right here afterwards
Also change Line 64 to:
KitApi.getInstance().register(PlayerList.getInstance(), new KitSelectorImpl(), this, Paths.get(String.valueOf(getDataFolder())));
Now you should go into the FFA and KitApi project and reload Gradle so:
open up the gradle sidebar on the right (Gradle) and click the Reload button.
Now go into the FFA Project, open the sidebar and locate
Tasks -> shadow -> shadowJar
double click shadowJar. On the left you will now see a build Folder in there, there should be a libs folder. Drag the hglabor-ffa-0.0.2.jar in your plugins Folder and run the server.
ENJOY! If there is any open question make sure to ask in the #coding channel on the HGLabor discord server
cheers,

Maquzo
