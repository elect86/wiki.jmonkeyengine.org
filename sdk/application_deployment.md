---
title: jMonkeyEngine SDK: Application Deployment
---
<h1 class="sectionedit1" id="jmonkeyengine_sdkapplication_deployment">jMonkeyEngine SDK: Application Deployment</h1>
<div class="level1">

<p>
After you have written and tested your game, you want to brand it and distribute it to your users. If you use the build script provided by the  jMonkeyEngine SDK's BaseGame, you have the following deployment options:
</p>
<ul>
<li class="level1"><div class="li"> Desktop application (.JAR)</div>
</li>
<li class="level1"><div class="li"> WebStart from <abbr title="Uniform Resource Locator">URL</abbr> (.JNLP + .JAR)</div>
</li>
<li class="level1"><div class="li"> Applet in web browser (.JNLP + .JAR)</div>
</li>
<li class="level1"><div class="li"> Android mobile device (.APK)</div>
</li>
<li class="level1"><div class="li"> iOS mobile device (XCode project)</div>
</li>
</ul>

</div>
<!-- EDIT1 SECTION "jMonkeyEngine SDK: Application Deployment" [1-455] -->
<h2 class="sectionedit2" id="requirements">Requirements</h2>
<div class="level2">

<p>
Since JAR files are platform independent, your customers can play your jMonkeyEngine application on Windows, Mac <abbr title="Operating System">OS</abbr>, or Linux. The only requirement is that the user has the free Java 5 or 6 Runtime (or browser plugin) installed. For more information see <a href="http://java.com" class="urlextern" title="http://java.com" rel="nofollow">http://java.com</a>.
</p>

</div>
<!-- EDIT2 SECTION "Requirements" [456-757] -->
<h2 class="sectionedit3" id="branding">Branding</h2>
<div class="level2">

<p>
<a href="/resources/sdk-jmonkey-branding.png" class="media" title="sdk:jmonkey-branding.png"><img src="/resources/sdk-jmonkey-branding.png" class="mediaright" alt="" width="420" height="216" /></a>
Make your game unique and recognizable:
</p>
<ol>
<li class="level1"><div class="li"> Open your game project in the SDK's Projects window.</div>
</li>
<li class="level1"><div class="li"> Right-click the project and open the Properties</div>
</li>
<li class="level1"><div class="li"> Open the Properties → Application section. Here you configure your branding:</div>
<ol>
<li class="level2"><div class="li"> Title: Enter the game's name</div>
</li>
<li class="level2"><div class="li"> Vendor: Enter your name (the development team)</div>
</li>
<li class="level2"><div class="li"> Description: Write one line why your game is the coolest ever <img src="/lib/images/smileys/icon_wink.gif" class="icon" alt=";-)" /></div>
</li>
<li class="level2"><div class="li"> Homepage: Enter your web <abbr title="Uniform Resource Locator">URL</abbr>, so your fans can find you</div>
</li>
<li class="level2"><div class="li"> Splashscreen: Browse to a cool screenshot that will be displayed while the game loads.</div>
</li>
</ol>
</li>
<li class="level1"><div class="li"> Click OK.</div>
</li>
<li class="level1"><div class="li"> Clean and Build. </div>
</li>
</ol>

<p>
Your executables are now branded.
</p>

<p>
TODO: where does this info actually show up?
</p>

</div>
<!-- EDIT3 SECTION "Branding" [758-1482] -->
<h2 class="sectionedit4" id="creating_the_distributable">Creating the Distributable</h2>
<div class="level2">

<p>
<a href="/resources/sdk-deploy_android.png" class="media" title="sdk:deploy_android.png"><img src="/resources/sdk-deploy_android.png" class="mediaright" alt="" width="335" height="220" /></a>
When you run the build script provided by the jMonkeyEngine SDK, it automatically compiles your classes, libraries, and assets. It creates a <code>dist</code> directory in your project directory which contains the executable JAR and a directory with libraries.
</p>

<p>
In the simplest case, you zip up the <code>dist</code> directory and distribute it to your customers. Companies often have additional tools to create executables and installers.
</p>

<p>
Here are your deployment options in detail:
</p>

</div>
<!-- EDIT4 SECTION "Creating the Distributable" [1483-2026] -->
<h3 class="sectionedit5" id="desktop_application_jar">Desktop Application (JAR)</h3>
<div class="level3">

<p>
The JAR file is the most common deployment method for Java desktop applications. The user downloads the executable JAR file to his machine and runs it to start the game.
</p>
<ol>
<li class="level1"><div class="li"> Right-click your project and open the Project Properties.</div>
</li>
<li class="level1"><div class="li"> In the Application&gt;Web Start category, make sure the box “Enable Web Start” is not checked. Click OK.</div>
</li>
<li class="level1"><div class="li"> Right-click your project and Clean and Build.</div>
</li>
<li class="level1"><div class="li"> If the build succeeds you see a line similar to  <br />
<code>Building jar: /home/joe/jMonkeyPlatform/MySuperTestGame/dist/MySuperTestGame.jar</code> <br />
this means the executable JAR has been generated successfully in your project directory.</div>
</li>
<li class="level1"><div class="li"> Zip up the <code>dist</code> directory and distribute it to your users. Make sure to keep the <code>lib</code> directory in it!</div>
</li>
</ol>

<p>
Most operating systems execute a JAR when users double-click on it, but you can also create a launcher.
</p>

</div>
<!-- EDIT5 SECTION "Desktop Application (JAR)" [2027-2903] -->
<h3 class="sectionedit6" id="desktop_executables_exe_app_jar">Desktop Executables (.EXE, .APP, .JAR)</h3>
<div class="level3">

<p>
jMonkeyEngine SDK allows you to create launchers for different desktop platforms, like an .exe file for Windows systems, an Application for MaxOSX and a launcher for Linux systems.
</p>
<ol>
<li class="level1"><div class="li"> Right-click your project and open the Project Properties.</div>
</li>
<li class="level1"><div class="li"> In the Application&gt;Desktop category, select the checkboxes for the platforms you want to distribute to.</div>
</li>
<li class="level1"><div class="li"> Click OK.</div>
</li>
</ol>

<p>
A <code>resources</code> folder in your project folder will be created that contains the template icons and settings files for each selected platform. If you change one of them, de-selecting the deployment for that platform will not delete this resource file anymore and it will not be overwritten when you re-enable deployment for that platform.
</p>

<p>
When you build your project, zip files for each selected platform will be created in the <code>dist</code> folder that contain all that is needed to run your application on that platform.
</p>

</div>
<!-- EDIT6 SECTION "Desktop Executables (.EXE, .APP, .JAR)" [2904-3837] -->
<h3 class="sectionedit7" id="web_start_jnlp">Web Start (.JNLP)</h3>
<div class="level3">

<p>
Web Start allows your users to start your application by simply clicking a link that you provide, for example in a button on your web page. The browser downloads the JAR file and then automatically runs your game in an extra window. The only requirement is that the user's browser has the Java plugin installed. This is a very user-friendly way for your customers to play your game without any extra steps to install it. Optionally, you can set it up so the file is saved to their desktop and can be restarted later, so they do not need to be online to play.
</p>
<ol>
<li class="level1"><div class="li"> Right-click your project and open the Project Properties.</div>
<ol>
<li class="level2"><div class="li"> In the Application&gt;Web Start category, check the box to Enable Web Start.</div>
</li>
<li class="level2"><div class="li"> Check the box to make the application self-signed. <img src="/lib/images/smileys/icon_exclaim.gif" class="icon" alt=":!:" /></div>
</li>
<li class="level2"><div class="li"> Optionally, check the box to allow offline use.</div>
</li>
<li class="level2"><div class="li"> Make sure <code>Application Descriptor</code> is activated. Click OK.</div>
</li>
</ol>
</li>
<li class="level1"><div class="li"> Right-click your project and Clean and Build. The <code>dist</code> directory is generated.</div>
</li>
<li class="level1"><div class="li"> Upload the contents of the <code>dist</code> directory to a public http server</div>
</li>
<li class="level1"><div class="li"> Either edit the sample launch.html file, or simply add a standard link (A HREF) pointing to your .jnlp file to one of your web pages.</div>
</li>
<li class="level1"><div class="li"> Tell your users to open your page in a webbrowser, and click the link to webstart the application.</div>
</li>
</ol>

<p>
Look at the sample launch.html, you can have any custom content around the link. Keep a copy of your launcher file because the jMonkeyEngine SDK will always regenerate its default launch.html.
Also, see this <a href="http://www.youtube.com/watch?v=oZnssg8TBWQ" class="urlextern" title="http://www.youtube.com/watch?v=oZnssg8TBWQ" rel="nofollow">demo video</a> on creating WebStarts.
</p>

</div>
<!-- EDIT7 SECTION "Web Start (.JNLP)" [3838-5441] -->
<h3 class="sectionedit8" id="browser_applet">Browser Applet</h3>
<div class="level3">

<p>
A browser Applet is a Java application that runs in the web browser while the user is visiting your web page. The only requirement is that the user's browser has the Java plugin installed. There is no installation step, the user can play right away in the browser. The user will not be able to save the game to his harddrive, nor can he play offline.
</p>

<p>
These instructions assume that you have already written a game that you want to turn into an Applet. As opposed to other jME3 games, Applets cannot capture the mouse for navigation, so the camera will be switched to dragToRotate mode. The jMonkeyEngine SDK and the included build script already contain what you need.
</p>

</div>

<h4 id="to_turn_a_project_into_an_applet">To Turn a Project Into an Applet</h4>
<div class="level4">
<ol>
<li class="level1"><div class="li"> Right-click your project and open the Project Properties.</div>
<ol>
<li class="level2"><div class="li"> In the Application&gt;Applet category, check the box to enable Applet creation.</div>
</li>
<li class="level2"><div class="li"> Change the applet width and height as you want it.</div>
</li>
<li class="level2"><div class="li"> Click OK.</div>
</li>
</ol>
</li>
<li class="level1"><div class="li"> Right-click your project and Clean and Build.</div>
</li>
</ol>

<p>
The <code>dist/Applet</code> directory now contains all the files necessary for the game to run as Applet. To test the Applet-based game, run the project in the jMonkeyEngine SDK.
</p>

</div>

<h4 id="to_deploy_the_game_as_applet">To Deploy the Game as Applet</h4>
<div class="level4">
<ol>
<li class="level1"><div class="li"> Edit the <code>dist/Applet/run-applet.html</code> file in anyway you like. Just keep the Applet code.</div>
</li>
<li class="level1"><div class="li"> Upload the contents of the <code>dist/Applet</code> directory to a public http server.</div>
</li>
<li class="level1"><div class="li"> Access the run-applet.html file using a webbrowser</div>
</li>
<li class="level1"><div class="li"> Click the link to web-start your application.</div>
</li>
</ol>

</div>

<h4 id="to_troubleshoot_applets">To Troubleshoot Applets</h4>
<div class="level4">
<ul>
<li class="level1"><div class="li"> Open the Java console for error messages.</div>
</li>
<li class="level1"><div class="li"> Depending on your settings, the browser caches the applet, the html page, and/or the jnlp file, even after you have cleaned and built the project. Make sure to empty the browser cache.</div>
</li>
</ul>

</div>
<!-- EDIT8 SECTION "Browser Applet" [5442-7206] -->
<h3 class="sectionedit9" id="android_mobile_device">Android Mobile Device</h3>
<div class="level3">

<p>
You can set the jMonkeyEngine SDK to build an executable for Android mobile platforms. 
</p>

<p>
Learn more about <a href="/jme3/android.html" class="wikilink1" title="jme3:android">Android Support</a> here.
</p>

</div>
<!-- EDIT9 SECTION "Android Mobile Device" [7207-7385] -->
<h3 class="sectionedit10" id="ios_device">iOS Device</h3>
<div class="level3">

<p>
You can set the jMonkeyEngine SDK to build an executable for iOS platforms. A Mac with XCode installed is needed.
</p>

<p>
Learn more about <a href="/jme3/ios.html" class="wikilink1" title="jme3:ios">iOS Support</a> here.
</p>

</div>
<!-- EDIT10 SECTION "iOS Device" [7386-7571] -->
<h2 class="sectionedit11" id="tipswitching_build_configurations">Tip: Switching Build Configurations</h2>
<div class="level2">

<p>
The jMonkeyEngine SDK has a Run Configuration menu in the toolbar. Use it to save your various sets of Project Property configuations, and switch between them.
</p>
<ol>
<li class="level1"><div class="li"> Click the <code>Set Project Configuration</code> popup in the toolbar and choose Customize.</div>
</li>
<li class="level1"><div class="li"> The Project Properties Run section opens. Under Configuration, click New.</div>
</li>
<li class="level1"><div class="li"> Name the saved configuration, for instance “my webstart” vs “my desktop app”, or “development” vs “deployment”. Click OK.</div>
</li>
<li class="level1"><div class="li"> Make sure the new config is selected in the <code>Set Project Configuration</code> popup above the editor.</div>
</li>
<li class="level1"><div class="li"> Make changes to the Project Properties as described above.</div>
</li>
</ol>

<p>
Now you can use the <code>Set Project Configuration</code> popup menu to switch between your run/build configurations.
</p>

</div>
<!-- EDIT11 SECTION "Tip: Switching Build Configurations" [7572-8347] -->
<h2 class="sectionedit12" id="tipreduce_distribution_file_size">Tip: Reduce Distribution File Size</h2>
<div class="level2">

<p>
There may be several parts of the full jMonkeyEngine library that you do not even use in your application. You should leave out the corresponding libraries from your distribution.
</p>

<p>
To remove unused libraries:
</p>
<ol>
<li class="level1"><div class="li"> Right-click your project and select “Properties”</div>
</li>
<li class="level1"><div class="li"> Select “Libraries” on the left</div>
</li>
<li class="level1"><div class="li"> Select the “jme3-libraries” entry and press “remove”. <br />
This library package contains <strong>all</strong> libraries for jME3 and is quite large.</div>
</li>
<li class="level1"><div class="li"> Press the “Add Library” button</div>
</li>
<li class="level1"><div class="li"> Select the “jme3-libraries-lwjgl-minimum” library</div>
</li>
<li class="level1"><div class="li"> Add other jME3 libraries in the same way depending which features you use: <br />
jme3-libraries-gui, jme3-libraries-physics, jme3-libraries-video, etc.</div>
</li>
<li class="level1"><div class="li"> Click OK.</div>
</li>
<li class="level1"><div class="li"> Clean, Build and Run the project and make sure you have not missed anything.</div>
</li>
</ol>
<div class="tags"><span>
	<a href="/tag/documentation.html" class="wikilink1" title="tag:documentation" rel="tag">documentation</a>,
	<a href="/tag/sdk.html" class="wikilink1" title="tag:sdk" rel="tag">sdk</a>,
	<a href="/tag/deployment.html" class="wikilink1" title="tag:deployment" rel="tag">deployment</a>,
	<a href="/tag/android.html" class="wikilink1" title="tag:android" rel="tag">android</a>,
	<a href="/tag/applet.html" class="wikilink1" title="tag:applet" rel="tag">applet</a>,
	<a href="/tag/webstart.html" class="wikilink1" title="tag:webstart" rel="tag">webstart</a>,
	<a href="/tag/desktop.html" class="wikilink1" title="tag:desktop" rel="tag">desktop</a>
</span></div>

</div>
<!-- EDIT12 SECTION "Tip: Reduce Distribution File Size" [8348-] -->
