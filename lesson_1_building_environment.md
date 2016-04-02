#Presiquites

###Install the JDK (Java Development Kit)

To develop Minecraft mods you must have the JDK installed. If you haven't already done this, follow these instructions.

1. [Click on this link ](http://www.oracle.com/technetwork/java/javase/downloads/index.html) to go to the Java SE Page
1. Click the Java (JDK) button to go to the JDK download page.
1. Accept the Licence Agreement before we can choose which version we want to download.
1. Click on the link for MacOS to start the download and launch the installer.
1. During the installation we will be asked where we want to install the JDK. We can leave the default directory.
1. Edit the environment variables, change the "path" variable and add the directory where we just installed the JDK followed by "\bin".
1. To check whether the environment variables are correct we can open up a new command prompt and type
javac

### Install Eclipse

1. [Click on this link](http://ftp.yz.yamagata-u.ac.jp/pub/eclipse//oomph/epp/mars/R2/eclipse-inst-mac64.tar.gz) to download eclipse installer
1. Run and select "Eclipse IDE for Java EE Developers"

### Install Minecraft Moddings

1. [Click on this link](http://files.minecraftforge.net/maven/net/minecraftforge/forge/1.9-12.16.0.1809-1.9/forge-1.9-12.16.0.1809-1.9-mdk.zip) to download Moddings version 1.9
1. Make a dev dir and move downloaded file into it
```
$mkdir -p ~/dev/minecraft
$mv ~/Download/forge-1.9-12.16.0.1809-1.9-mdk.zip ~/dev/minecraft/
$cd ~/dev/minecraft
$unzip forge-1.9-12.16.0.1809-1.9-mdk.zip
$rm forge-1.9-12.16.0.1809-1.9-mdk.zip
$mv forge-1.9-12.16.0.1809-1.9-mdk Forge
```
3. Prepare the moddings environment, this will take a long time
```
$cd ~/dev/minecraft/Forge
./gradlew setupDecompWorkspace
```
3. Create workspace for Eclipse
```
$./gradlew eclipse
```

#Create a Moddings Projects
The structure of `minecraft` folder will be like this after this
```
├── Forge
│   ├── gradle
│   ├── gradlew
│   ├── gradlew.bat
│   ├── run
│   ├── eclipse
│   ....
```

1. Open Eclipse change your workspace in to `~/dev/minecraft/Forge/elipse`
1. Add into `src/main/java` source folder, file `ExampleMod.Java` these following:
```
@EventHandler
public void preInit(FMLInitializationEvent event) {
  System.out.println("--------------------------------------------------------- Preinit >> Hollla");
}

@EventHandler
public void init(FMLInitializationEvent event)
{
// some example code
    System.out.println("--------------------------------------------------------- DIRT BLOCK >> "+Blocks.dirt.getUnlocalizedName());
}

@EventHandler
public void postInit(FMLInitializationEvent event) {
  System.out.println("--------------------------------------------------------- Postinit >> Hollla");
}
```

1. That's it, let's start the server and observe these messages is print in the console.

```
[17:11:43] [Client thread/INFO] [STDOUT]: [com.example.examplemod.ExampleMod:init:23]: --------------------------------------------------------- DIRT BLOCK >> tile.dirt
[17:11:43] [Client thread/INFO] [STDOUT]: [com.example.examplemod.ExampleMod:preInit:16]: --------------------------------------------------------- Preinit >> Hollla
[17:11:43] [Client thread/INFO] [STDOUT]: [com.example.examplemod.ExampleMod:postInit:28]: --------------------------------------------------------- Postinit >> Hollla
```
