# MAC Executable

```
javac ShowTime.java
java ShowTime

echo "Main-Class: ShowTime" > MainClass.txt
cat MainClass.txt

jar cmfv MainClass.txt ShowTime.jar *.class

java -jar ShowTime.jar

jpackage --name ShowTime --input . --main-jar ShowTime.jar \
   --resource-dir package/macos --type pkg
ls -o *.pkg

```

The executable JAR file ShowTime.jar checks in at a mere 0.001 MB, but the installer file ShowTime-1.0.pkg almost hits a whopping 50 MB.  
The reason is that the installer bundles the JRE (an Apple requirement for publishing Java programs to the Mac App Store).
