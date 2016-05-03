[< back](https://github.com/camb416/project-tutorials)

# Write Processing 3 sketches in IntelliJ IDEA.

This tutorial covers Processing 3 in IntelliJ IDEA 15 Community Edition (CE) on Mac OS X.


## Getting a Java Development Kit

First, you need to have a Java JDK installed. [Download one from Oracle](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html). and Install it.

## Getting IntelliJ IDEA

You can [download IntelliJ IDEA Community Edition](https://www.jetbrains.com/idea/download/) for free from JetBrains.

## Creating a Project

Run IntelliJ IDEA and select **Create a new Project**.

Select **Java** on the top left, then select the JDK you installed in the Project SDK Dropdown. If you do not see it installed, click `New > JDK`. IntelliJ should automatically select the right folder, then click OK, then click **Next**. 

Do Nothing and click **Next**.

Call your Project Name `projectname` and click **Finish**.

## Adding Processing libraries

Click File > Project Structure and Select Libraries in the left column.

Click the + and select "Java".

Assuming your Processing IDE is installed in the default location, you should find `core.jar` at "/Applications/Processing.app/Contents/Java/core.jar". Select the file and Click OK.

Click OK to select the only Module (named `projectname`). Click OK again to exit "Project Structure".

## Creating Scaffolding Code

Right click on the src folder in the left column and select `New > Package`. Call name the package something unique. Here we will use `com.wearesubrosa.projectname`.

Right click on the package you just created and Select `New > Java Class`. Call it `Main`. 

Repeat the process to create another Java Class and call it `app`.

Copy this code into the `app` class (change your package name to match yours):
```
package com.wearesubrosa.projectname;
import processing.core.PApplet;

/**
 * Created by cameron.browning on 5/3/16.
 */
public class app extends PApplet {

    public void settings(){
        size(720,480);
    }

public void setup(){
    background(255);
}
    public void draw(){
        stroke(0);
        line(random(width), random(height),random(width), random(height));
    }

}
```

And then use this code for the Main class:
```
package com.wearesubrosa.projectname;
import processing.core.PApplet;

/**
 * Created by cameron.browning on 5/3/16.
 */
public class Main {
    public static void main(String args[]){
        // pass string for fullscreen
        PApplet.main(new String[] {"com.wearesubrosa.projectname.app"});
    }
}
```

## Running your Processing Application

Select `Run > Edit Configurations` from the menu.

Select `Application` from under `Defaults`.

Enter `com.wearesubrosa.projectname.Main` into the Main class field and click OK.

## Saving as a Template

Once you complete this, you can select `Tools > Save Project As Template`. Enter `Processing Project` in the Name and enter a description and click OK.

Next time you want to create a Processing Project, you can select "Processing Project" from under "User-defined" in the left column of the New Project window.

When creating from a template, you should rename the last part of the Base package, and the Project Name.

Thanks to Andreas Linz, who wrote another [great, and frankly more thorough tutorial](https://blog.klingt.net/posts/processing-2-in-intellij-idea-14/) on this topic .