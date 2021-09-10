# 🐨 Koala UI

#### Requires Python 2.7. (If you have macOS, maybe python is already instaled, if not install from link https://www.python.org/downloads/macos/)

## Configuration:
- Create a /Scripts folder in you project in Terminal<br>
> <code>mkdir Scripts</code><br>
> <code>cd Scripts</code><br>
- Inside /Scripts folder, download the GWB from apple git repo with command below.<br>
> <code>wget https://raw.githubusercontent.com/apple/swift/main/utils/gyb</code><br>
> <code>wget https://raw.githubusercontent.com/apple/swift/main/utils/gyb.py</code><br>
- Set write permission to files.<br>
> <code>chmod +x gyb</code><br>
> <code>chmod +x gyb.py</code>

- In your terminal, inside /Scripts folder execute the code:
> <code>wget https://raw.githubusercontent.com/leobmaffei/koalaUI/main/Scripts/generateTagFiles.sh</code><br>
#### In the next step you can create your folders in location wherever you want, I will demonstrate in based on root folder.
#### Pay atention to paths if you decide to create the folder in other location
- In Xcode criate a folder called "DesignSystem"
- In Design System folder create a new Folder with name "CodeGen"
- In CodeGen folder create a new Empty Type file with the name "DesignSystemTokens.swift.gyb"
> This file execute Swift + Python code to generate your tokens automatically
- Copy and paste the code bellow into your DesignSystemTokens.swift.gyb file
<code>Insert Code Here</code>
- In DesignSystem/CodeGen folder create a new Swift file with the name "DesignSystemTokens.swift" and let this file empty for now
- Download my example of JSON Design System Token file and add to DesignSystem. folder. Fell free to change the token hierarchy and values.
> JSON recommended example
> > https://github.com/leobmaffei/koalaUI/blob/main/koalaUI/DesignSystem/Design_System_Tokens.json
- Insert the json file in the Design System folder selecting "Copy files if Needed"

- On your Build Phases click in the plus("+") button
- Select New Run Script (you can rename it, to easier identification)
- Your run script needs to be right before "Compile Sources" otherwise you get the error "Cycle inside koalaUI; building could produce unreliable results. This usually can be resolved by moving the target's Headers build phase before Compile Sources."
- Insert the Code below:
> <code>${PROJECT_DIR}/Scripts/generateTagFiles.sh</code>
- Insite Input Files add the path: (if you are using another path for your files, add you custom path)
<code>${PROJECT_DIR}/DesignSystem/CodeGen/DesignSystemTokens.swift.gyb</code>
- Insite Output Files add the path: (if you are using another path for your files, add you custom path)
<code>${PROJECT_DIR}/DesignSystem/CodeGen/DesignSystemTokens.swift</code>
- Congrats, now your setuoo is done. You can test by writing ssometing in the DesignSystemTokens.swift.gyb file, saving and cheching the DesignSystemTokens.swift file. If the text appears there, the configuration was succeeded.
- Now, copy this code bellow and paste in DesignSystemTokens.swift.gyb (please be careful with the code identation python will not work with wrong identation)
<code>https://github.com/leobmaffei/koalaUI/blob/main/koalaUI/DesignSystem/CodeGen/DesignSystemTokens.swift.gyb<\code>


> Use this only if you got permisssion error when build project, use: <code>chmod u+x generateTagFiles.sh</code>

