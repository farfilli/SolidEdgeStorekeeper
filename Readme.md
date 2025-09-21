﻿<div class="center">
  <p align=center>
  <img src="media/logo.png" width=50%;>
  <p align=center>
  <span class="description">Robert McAnany 2025</span>
</div>

## CREDITS

**Contributors**  
@[Francesco Arfilli], @TeeVar

**Beta Testers**  
@hawcad, @rob.wolbrink7456, @[Francesco Arfilli], @pedja, @TeeVar, @Seva

**Helpful feedback and bug reports**  
@SeanCresswell, @[Francesco Arfilli], @arekkul, @[Imre Szucs], @64Pacific, @Seva, @hawcad, @rob.wolbrink7456, @pedja, @TeeVar

*Feedback from users*

> OMG .....love your work buddy!

>  Management of standard parts is a huge use of my time and this may solve that!

> Thx, another great tool for SolidEdge​ Users!

> Cool tool!  I have been looking for something just like this.  (...) Great job, and making it open source is just extra good karma.

> Another excellent utility. Appreciate your contributions to the community. 

## DESCRIPTION

Solid Edge Storekeeper is a utility to create, organize, and share standard parts.  It is free and open source and you can find it [<ins>**Here**</ins>](https://github.com/rmcanany/SolidEdgeStorekeeper#readme).  Please note the standard part templates were created with SE2024.  You will need that version or newer to use them.  (Update: A user, **@TeeVar**, generously contributed a set of templates created with SE2019.)

Fasteners, retainers, structural shapes, and more in ANSI and ISO format are included.  There are over 15k items available.  There is no database; everything is done in Excel.  It is fully customizable.  If you upgrade Solid Edge, no change to the program or its data is required.

The program handles two types of standard parts.  One consists of items like fasteners.  These are defined in dimension tables and created as needed.  The other consists of vendor-type items like pneumatic fittings.  Each of these has its own model file.  Both types are eligible for the handy automatic patterning option.

### Tree Search

<p align="center">
  <img src="media/tree_search.png">
</p>

For items like fasteners, use **Tree Search**.  Navigate to the desired item, right-click and choose an action. If the part is not already in the library, the program creates it and saves it in the library.  The possible actions are:

- `Add to assembly`  Adds the part to the assembly and activates the `Place part` command.
- `Replace selected`  Replaces a selected part in the assembly.
- `Replace all`  Replaces all occurrences of a selected part in the assembly.
- `Fastener stack`  Opens the fastener stack dialog.  See the separate section below for details.

Note, depending how the data is set up, you may be prompted to select a material after choosing an action.  Once chosen, the setting persists.  To reset it, click the material name on the toolbar.

### Property Search

<p align="center">
  <img src="media/property_search.png">
</p>

For vendor-type parts, use **Property Search**.  Enter the search terms, then click ![Search Button](media/icons8-search-16.png).  Locate the desired item on the list, then right-click and select `Add to assembly`.  Note, the program does not come with any of these; you're on you own for that.  Simply add what you need (and probably already have) to the library, in a subdirectory if you prefer.  

That's pretty much all there is to know about vendor type parts.  For the others, a bit more information follows.

You can set the file names according to your preference.  You can specify the material or any other SE file property.  File names and properties can accept formulas as input.  So you can do stuff like:

![Filename Formula](media/filename_formula.png)

Structural shapes are not quite the same as fasteners.  While the cross section is standard, the length and the possibility of additional features is not.  Usually the part doesn't even belong in the library.  For these, you can change the `Save in` option from `Library` to `Other`.  Rather than assuming a name and location, with this setting the program prompts for both.

Unlike Family of Parts, files are only created as needed.  Also, each part is stand-alone, not tied back to a master file.

Unlike web-based offerings, the program is integrated with your parts library and works directly with Solid Edge.  It updates the properties you specify, using the naming conventions you define.  If you want adjustable parts (see the provided springs example), or any other SE-specific functionality, the program handles it like the native file that it is.

The program will never have every standard part in the world, but it can be improved.  That's where **YOU** come in!  Contributions are welcome.  Please message me on the [<ins>**Solid Edge Forum**</ins>](https://community.sw.siemens.com/s/topic/0TO4O000000MihiWAC/solid-edge), or raise an [<ins>**Issue on GitHub**</ins>](https://github.com/rmcanany/SolidEdgeStorekeeper/issues), for ideas on how to get started.

Uh-oh.  The Marketing guy just showed up.  He wants to *"Synergize our stake holders and leverage this cross-promotion opportunity"*.  Who talks like that?  Anyway, here he is.

>  *Hello there!! I'm Big Mike!  Do you want to do things better and faster with less work?!  Of course you do!  That's why you need [<ins>**Solid Edge Housekeeper**</ins>](https://github.com/rmcanany/SolidEdgeHousekeeper#readme)!  It is a batch utility for finding annoying little errors in your project!  You're going to love it!!*

Sorry about that.  Let's move on.

## INSTALLATION

Please note there is some setup required before using the program.  After completing this step, check the **Setup** section below for details.

To install, do one of the following
- Download the [<ins>**Latest Release**</ins>](https://github.com/rmcanany/SolidEdgeStorekeeper/releases) (It will be at the top of the page)
- [<ins>**Clone the Project**</ins>](https://github.com/rmcanany/SolidEdgeStorekeeper) (See below to get the data and templates)

### Downloading the Latest Release

<p align="center">
  <img src="media/release_page.png">
</p>

To get the latest release, click the file `SolidEdgeStorekeeper-VYYYY.N.zip`.  You may have to expand the Assets dropdown to see it.  Your browser should prompt you to save it. 

Choose a convenient location on your machine. Extract the zip file (right-click > Extract All).  Verify the directory is not blocked or read-only (right-click > Properties).  The program needs to be unblocked with write access to function properly.  

Double-click `Storekeeper.exe` to run.  The first time you do, you may get a `Windows Protected Your PC` message.  You can click `More Info` followed by `Run Anyway` to launch the program. 

### Cloning

The data and templates are not in the GitHub repo.  You need to download a Release to get them.  To make them available in your development environment, copy the directories `DefaultDataSE2019`, `DefaultTemplatesSE2019`, `DefaultDataSE2024`, `DefaultTemplatesSE2024` to the locations where your compiled `Storekeeper.exe` is located.

On my machine, the executable resides in two places: `bin\Debug\net8.0-windows\` and `bin\Release\net8.0-windows\`.  I have copies of those directories in both places.

## SETUP

As noted earlier, some setup is required before using the program.  If you run Solid Edge in a localized language please be sure to see the information at the end of this section.

### Tree Search Options

The program needs to know where to store the standard parts, and for fastener-like items, where to find the files defining their shape and spreadsheet containing their dimensions.  The settings are accessed on the **Tree Search Options** page.  Click ![Options](media/Support_16.png) on the toolbar to open it.

<p align="center">
  <img src="media/tree_search_options.png">
</p>

- **LIBRARY DIRECTORY**  
The library is where the standard parts you create are stored.  The default is in `Preferences\Library` under the `Storekeeper` main directory.  

  Note it is created the first time you run the program; it won't be there before that.  As noted above, if you want to access your vendor-type standard parts, they must be in the library.  You can place them in one or more subdirectories if desired.

- **TEMPLATE DIRECTORY**  
The templates are SE part files that have variable-table-driven geometry to create new parts of a given type.  By default they are stored in the `Preferences\TemplatesSE2024` folder.

  As noted at the outset, the original templates were created in SE2024.  They will only work if you're using that version or newer.  An alternative set of templates, created with SE2019, was generously contributed by **@TeeVar**.  To use them, change the template directory to `Preferences\TemplatesSE2019`.  

  Even if you have a newer version of Solid Edge, you may still want to use the SE2019 templates.  Unlike me, **@TeeVar** is an ISO native speaker.  If you work with that standard, his naming conventions will probably be more familiar and useful to you.

  Note, the templates and the spreadsheet that drives them go together.  If you change one, you have to change the other.

  You don't have to stick with your first choice, by the way.  You can switch between the original and alternative templates as needed.

- **DATA DIRECTORY**  
The spreadsheet contains the variables required for each size of each type of part.  By default, it is stored in the `Preferences\DataSE2024` directory. 

  Change the data directory to `Preferences\DataSE2019` if you want to use the alternative templates.  You will have to restart the program for the change to take effect.

- **MATERIAL TABLE**  
The material table is usually your normal SE material table.  However, for a quick test of the program, an alternative is to use `Storekeeper.mtl` from `Preferences\Templates`.  Copy it to your Solid Edge Materials directory to make it available.  On my machine, that location is `C:\Program Files\Siemens\Solid Edge 2024\Preferences\Materials`.  

  If you decide to continue using the program, you would eventually want to utilize your own material table, updating material names in the spreadsheet and templates as needed. 

- **OPTIONS**
  - `Read the Excel file each time the program is launched`  
	Internally, the Excel file is parsed and saved in `*.xml` format.  If you haven't changed the Excel file, this is an unnecessary step.  Clearing this option tells the program to use the `*.xml` file it created previously.
  - `Automatically pattern a part assembled to a patterned feature`  
	Standard parts, especially fasteners, are often patterned after placement.  The program can detect if a face used to assemble the item is part of a pattern.  
	 
	This works with `Smart Patterns` and `User-Defined Patterns` (that's a hole with multiple hole circles in the profile).  It does not currently work with (the default) `Fast Patterns` unfortunately, unless you get lucky and pick the hole that was used to create the pattern.
  - `Add any property not already in file`  
	As mentioned above, besides creating geometry, the program can also update file properties.  Enabling this option tells the program to add any (custom) property not already in the file.
	
  - `Disable fine thread warning`  
	The program is currently unable to properly set the thread size for ANSI UNF external threads.  The program logs a warning if this occurs.  Enabling this option suppresses that warning.
	
	The condition can cause issues with interference checking.  Fixing it is optional.  To do so, open the file and edit the Thread definition.  On the Parameters Step, you'll note the size designation is followed by an asterix (*).  Click the drop down and select the one without it.
	
	![Thread Fix](media/fine_thread_fix.png)
	
  - `Process templates in background`  
	A new part must be opened in Solid Edge to update its parameters.  This setting tells the program to not display it in the user interface.

	Note, processing in background does not support `Fit View`.  If you need usable thumbnail images, this option is probably not for you.

	Also note, there is an issue when creating a part whose units do not match the default units of your Solid Edge installation.  Processing in background appears to ignore the file's unit setting.
	
  - `Replace part: Suppress failed constraint`  
	When replacing a part, some constraints may fail to get resolved.  If this occurs, this option tells the program to suppress the constraint.
	
  - `Replace part: Allow failed constraint`  
	With the same situation as above, this option tells the program to leave the constraint in the failed state.
	
  - `Do not add files in the Recently Used list`  
	Enable this option to keep the program from adding newly-generated standard parts to the Most Recently Used list.  Note this function was added to Solid Edge in version 2020.  If you are running an earlier version, this option must be disabled.
	
  - `Allow comma delimiters (experimental)`  
	Allows the use of a comma as the decimal delimiter.  This is somewhat experimental because commas are not allowed `*.xml` headers.  There is a workaround in place, but has not been thouroughly tested.  Disabling this option causes causes commas to be replaced with periods in the `*.xml` file.
	
  - `Storekeeper always on top`  
	Keeps the storekeeper dialog on top of other windows.

  - `Include drawing of part if present`  
	If a file in the templates directory has an associated drawing, the program can copy it to the library along with the part.  Enable this option to do so.

  - `Check for new version at startup`  
	If you don't need a reminder about new versions, disable the check here.

### Property Search Options

Additional settings for **Property Search** are accessed from that tab's toolbar.  Click the **Property Search Options** button ![Options](media/Support_16.png) to display the form.

<p align="center">
  <img src="media/property_search_options.png">
</p>

#### Properties to Search

This is where you enter the names of the properties that hold the values you want to match.  You must also specify if the property is System or Custom.  System properties are in every Solid Edge file.  Custom properties are ones you define, probably in a template.

#### Solid Edge Template Files


These are your normal template files, not the ones used by the program to create standard parts.  They are needed to populate the available properties, and to determine what language is in use.

#### Options

- `Cache library file properties for faster search`  
  Reads all file properties and saves them in a separate file.  This can speed up property searches for large libraries.  It takes some time to load the file initially; the status bar informs you of the progress.

### Localized SE Installations

You may have more work to do if you're not using English in Solid Edge.  In the spreadsheet `Storekeeper.xls`, there are some property names that probably need to be changed.

Open the file (located in the `Preferences\Data` directory) and look for entries like `%{System.Title}` and update as required.

## FASTENER STACK

A fastener stack is a grouping that consists of a fastener and related components, such as washers and nuts.  To create one, on the `Tree Search` dialog, right-click a fastener and select the `Fastener stack` command.  The following form is shown.

<p align="center">
  <img src="media/fastener_stack.png">
</p>

To select the stack style, click the `Configuration` button.  There are eight versions that employ nuts, and four each for thru and blind tapped holes.  Note, you only choose the fastener.  The related components are automatically selected based on the fastener diameter and thread.

<p align="center">
  <img src="media/fastener_stack_configuration.png">
</p>

Once the desired configuration is selected, choose the units and enter the appropriate parameters.  Click `Add to Assy` to start the process.  

The program first searches the library for a fastener length that meets the criteria.  If none is found, an error is diplayed.

If a fastener is found, the program then opens separate temporary subassemblies for the top and bottom parts of the stack, and populates them with the components you chose.

Next, it adds each updated subassembly, in turn, to the main assembly.  The subassembly is dispersed into the main assembly and the `Place part` command is activated.

The program waits for the `Place part` command to finish before proceeding.  Confusingly, the command does not automatically finish when the parts have been fully constrained.  You have to either right-click the mouse or press the `Escape` key.  If you notice nothing happening for a while, the program could be waiting for your input.

After the components are placed, they are converted to an `Assembly group`.  Finally, the group is patterned if applicable, assuming that option is enabled.



## PRE-POPULATING THE LIBRARY

You can add items to the library ahead of time.  Enable the `Pre-populate` checkbox to get started.

<p align="center">
  <img src="media/prepopulate_library.png">
</p>

To select an item, enable its checkbox.  Enabling the checkbox of a category header will select all items (including subcategories) below it.  You can select a category, then de-select any items you don't want included.  

Once satisfied with the selection, click `Add to library` to start the process.  After you do, the `Close` button text changes to `Stop`.  Click that to stop processing.  It may take a few seconds to register.  It doesn't hurt to click it twice.

To avoid confusion, the `Add to assembly` shortcut is disabled in this mode.  Uncheck `Pre-populate` to get it back.

One handy feature missing in the `TreeView` control is `Multiselect`.  That means you cannot select a range with click followed by SHIFT-click.  It may be possible to add code to implement it, but it's not available now.


## CREATING NEW TEMPLATES

You are of course free to create new templates any way you see fit.  However, if you plan to contribute your awesome work to the project, there are a couple of things to keep in mind.

<p align="center">
  <img src="media/template_axes.png">
</p>

Many standard parts have a primary axis.  For consistency, consider orienting it along the Y Axis as shown.  For parts with a secondary axis like the pipe elbow, consider the Z Axis.

Another thing to think about is the effect of replacing one standard part with another.  It would be nice not to break assembly relationships.  For fasteners, I started with the socket head capscrew.  When it was time to create the next one, I did a Save As on that initial part and modified it as needed.  Since the head and body now have the same faces, Replace Part works as expected.

<p align="center">
  <img src="media/template_variable_names.png">
</p>

Variable names are something else to consider.  To minimize confusion in creating and maintaining the companion spreadsheets, see if you can reuse names that have been previously established.  You can check the supplied templates or spreadsheets to see what may apply to your parts.

I don't know where to mention this, so I'll do it here.  Some standard parts require a drawing.  That is supported as an option.  Simply create a drawing with the same name as the template.  If the program finds such a drawing, and the option is enabled, it copies it to the library, renames it and updates the links.  Enable the option `Include drawing of part if present` on the **Tree Search Options** page.

## CUSTOMIZATION

The following is for those who want to customize the program.  You may want to do that eventually, but you can safely skip this section if you're just getting started.

### Organization

Earlier I referred to "a spreadsheet."  In reality there are multiple spreadsheets.  One, `Storekeeper.xls`, is the place where the overall layout of the data is handled.  The others are companion files that hold detailed information about a given category of parts.  These have names like `AnsiFasteners.xls`, `IsoStructural.xls`, etc.

While the use of Excel is handy, it's not all roses.  Representing an arbitrary-depth heirarchical tree is awkward, for one thing.  Here is how `Storekeeper.xls` is organized.

<p align="center">
  <img src="media/excel_top_level.png">
</p>

You'll see that the tree structure is represented by indenting.  The top node is `Solid_Edge_Storekeeper` and in this example its first child node is `Ansi_Fasteners_Steel`.  The first two child nodes under that are `BHCS` and `FHCS`.

In addition to child nodes under any given node, you'll notice other entries.  Those are some program attributes being set, and various properties being assigned.  More about properties in a bit.

In the image, the `BHCS` and `FHCS` nodes each have an entry, `Nodes` (plural).  That is one of those program attributes just mentioned.  It is the mechanism that tells the program to consult a companion spreadsheet tab for further information.  Here is a small portion of the companion data for Dowel Pins.

<p align="center">
  <img src="media/companion_spreadsheet.png">
</p>

The rows represent different sizes, the columns represent values for a given size.  The first row holds the name for each value, the second holds its *type*.  The first column tells the program whether or not to display a given size.  It's for reducing clutter in the interface.

The types `Variable` and `LeafNodeVariable` refer to entries in the template's variable table.  One other *type* not shown in the image is `ParameterString`.  That denotes a value that is needed in the template, but does not reside in the variable table.  For those,  there must be separate code to handle it.  Currently only `ThreadDescription` is supported.  See `AnsiFasteners.xls` for an example.

### Properties and Spreadsheet Variables

Now, let's look at the other entries in `Storekeeper.xls`, starting at the top.  

#### Top Level of the Tree

<p align="center">
  <img src="media/properties_top_level.png">
</p>

Here at the top level of the tree, we are defining spreadsheet variables for property names and the corresponding name in the Solid Edge file.  The location of the definition in the tree defines its scope.  Since these statements are at the top of the tree, they apply everywhere.

The syntax is horrible; that's how Xml likes it.  While Xml is a very flexible data-representation format, it is quite rigid in this regard.

#### Next Level Down

<p align="center">
  <img src="media/properties_ansi_fasteners_steel.png">
</p>

In this image, we are looking at a tree node one level below the top.  You'll see we are setting values for the part number, hardware status and material.  

The name of the spreadsheet variable has rules.  `XyzProperty` looks for `XyzFormula` to know how to proceed.  The prefix, `Xyz` in this case, can be anything you want (except for some reserved names shown below).  The suffix, `Property` and `Formula`, are the only valid choices.  

**Reserved Spreadsheet Variables**
- TemplateProperty
- TemplateFormula
- FilenameProperty
- FilenameFormula
- MaterialProperty
- MaterialFormula
- Node
- Nodes

So, for example to update the part number in the file, the program will use the information in `PartNumberFormula` to update the property defined in `PartNumberProperty`.  In this example that tells the program to make this assignment.

`%{System.Document Number} = "NA"`

#### One More Level Down

<p align="center">
  <img src="media/properties_bhcs.png">
</p>

Here we are setting up the processing of button head capscrews.  You can see we need to specify what template to use and how to name the file.  We must also provide the companion spreadsheet name and the tab in that file where the information is stored.  

As mentioned previously, formulas can contain entries such as `%{Name}` and `%{Length}`.  Variables not proceeded by `System.` or `Custom.` are assumed to come from the companion spreadsheet.

In this example, we are also updating the description property.  That isn't necessary for the program to function.  It just illustrates how to update Solid Edge file properties.  Any property in the file can be updated in this way.  

## OPEN SOURCE PACKAGES

This project uses these awesome open source packages.

- Excel reader [<ins>**ExcelDataReader**</ins>](https://github.com/ExcelDataReader/ExcelDataReader)
- File and folder dialogs [<ins>**CommonFileDialogs**</ins>](https://github.com/emako/CommonFileDialogs)
- Icons [<ins>**Icons8**</ins>](https://icons8.com)
- JSON Converter [<ins>**Newtonsoft.Json**</ins>](https://github.com/JamesNK/Newtonsoft.Json)
- Structured storage editor [<ins>**OpenMCDF**</ins>](https://github.com/ironfede/openmcdf)
