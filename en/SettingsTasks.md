---
redirect_from:
 - /ru/SettingsTasks.html

title: "ConEmu | Settings › Tasks page"

breadcrumbs:
 - url: TableOfContents.html#settings
   title: Settings

readalso:
 - url: Tasks.html
   title: "Tasks: Set up your favourite shells"
 - url: CommandLine.html
   title: "GUI, Console and Shells switches"
 - url: NewConsole.html
   title: "-new_console and -cur_console"
---

# Settings: Tasks

{% comment %}
This page was manually edited
{% endcomment %}

{% comment %} IDD_SPG_TASKS {% endcomment %}


![ConEmu Settings: Tasks](/img/Settings-Tasks.png)

ConEmu's [**Tasks**](Tasks.html) are used to store predefined commands
or [shell's](TerminalVsShell.html) command lines
to run them anytime later by name or hotkey.


## Predefined tasks (command groups)  {#id2115}

**Task name**, surrounded by {...}, may be used in
<a href="ToolBar.html"><code class="plus">[+]</code> menu</a>,
[Recreate dialog](LaunchNewTab.html#Create_new_console_dialog),
[-run argument](ConEmuArgs.html) of ConEmu.exe
or even in prompt via [ConEmuC.exe -c {task name}](ConEmuC.html#Commands).


#### Hotkey  {#id2628}

Choose hotkey for creating this Task (it's not [global](GlobalHotKeys.html) and works in ConEmu only).


#### Default task for new console  {#id2750}

Only one Task may be marked as *default task*, than it will be used when user [starts new console](LaunchNewTab.html)
by <code class="plus">[+]</code> button or [Create new console hotkey](SettingsHotkeys.html) (`Win+W` by default).


#### Taskbar jump lists  {#id2752}

Check this box if you want to use the Task from [Task bar jump list](Windows7Taskbar.html).
Don't forget to save the settings and [update jump list](SettingsTaskBar.html).


#### Default shell (Win+X)  {#id2751}

Choose the Task which should be started by `Win+X` [hotkey](SettingsHotkeys.html) (works in ConEmu only).


#### Task parameters  {#id2322}

This field may contain some optional switches like startup directory or icon.
Here you may set the [tab](TabBar.html) icon, [startup directory](StartupDir.html),
control if Task should be started in existing or new ConEmu window, etc.

Full set of allowed switches is described here: [Tasks parameters](Tasks.html#task-parameters).

Example:
```
/dir "C:\\" -icon "cmd.exe" -single
```


#### Commands  {#id2118}

Specify here an application, arguments and [-new_console](NewConsole.html#syntax) parameters.

One Task may start one console or group of consoles, one line in Commands starts one console.
Delimit commands with empty lines.

For convenience some shortcuts are allowed here:

* Prefix `>` to mark active console, an alias for [-new_console:f](NewConsole.html#syntax).
* Prefix `*` to start console 'As Administrator', an alias for [-new_console:a](NewConsole.html#syntax).

Example: run two consoles - Visual Studio and Powershell prompts. VS tab remains active, both are started elevated.

```
>* cmd /k ""C:\Program Files (x86)\Microsoft Visual Studio\2019\Professional\Common7\Tools\VsDevCmd.bat"" -new_console:t:"VS 2019"
* pwsh
```

Read about [-new_console](NewConsole.html#syntax) switches to undestand full set
of possible options to control console start up.

One-level one-liner Tasks **nesting** is supported.
E.g. if you define the `{MyTool}` task, you may create another task `{ToolSet}` with nested tasks.
You may also run them in [splits](SplitScreen.html).

```
{MyTool} parameter-set-1
{MyTool} parameter-set-2
{MyTool} parameter-set-3
```


#### Add/refresh default tasks...  {#id2632}

**Default Tasks** are some predefined [Tasks](Tasks.html) generated by ConEmu
for well known shells and toolsets.

This button refreshes [default tasks](DefaultTasks.html) asking for action:
Add only new tasks (e.g. new Visual Studio version was installed)
or refresh contents of existing tasks too.


#### Reload...  {#id2131}

Reload Tasks from [settings storage](Settings.html).
Useful during experiments with configurations.
Works till ‘Save settings’ button is pressed.


#### Clone  {#id3087}

Create a copy of the selected Task. New Task is placed just below the current one.


#### + (button)  {#id2122}

Create a new empty Task.


#### - (button)  {#id2124}

Delete the selected Task after confirmation.


#### Up  {#id2126}

Move selected Task upwards.


#### Down  {#id2127}

Move selected Task downwards.


#### Tab...  {#id2128}

Open the [New console dialog](LaunchNewTab.html) and append
the result to [Task Commands](#id2118). Useful to configure multiple options
and [-new_console](NewConsole.html#syntax) switches in a visual way.


#### Startup dir...  {#id2452}

Open Windows choose folder dialog and append [-new_console:d:"directory"](NewConsole.html#syntax)
switch to [Task Commands](#id2118).


#### File path...  {#id2129}

Open Windows choose file dialog and append the path to [Task Commands](#id2118).


#### Active tabs  {#id2493}

Append running in the ConEmu consoles to [Task Commands](#id2118).
This is useful to configure multiple splitted consoles started manually before.
