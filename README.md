Better Blender
==============

This Windows Blender 2.78c fork was created out of various frustrations I had with Blender, the 3D modeling/animation application.

Most of these changes were related to usability issues that I had with the application. I made sure not to do anything that would change the file format, so any files created with this version of Blender will be compatible with the non-modified version of Blender 2.78c. (The only slight exception is the "Set Start Frame for Background Video" feature, which will behave differently in the non-modified version of Blender.)

Here are the changes:

* **Obnoxious Headers:** Many of Blender's keyboard shortcuts depend on which window your mouse cursor is hovering over. Unfortunately, Blender does not make it very obvious which window your mouse cursor is hovering over, and if you have a large screen or two monitors, it's not always immediately obvious where your mouse cursor is. As a result, I've implemented "obnoxious headers" which, while not pretty, make it blatantly obvious where your mouse cursor is at all times.

* **Eliminate Popup Boxes:** I found it to be a tremendous headache to choose a menu option and then have a tiny, non-standard weird confirmation dialog box pop up in roughly the same position as the mouse cursor. Because the dialog box was so tiny, I often clicked outside of it (or didn't even see the it), having to perform the operation again. These tiny boxes have been replaced with standard modal Windows dialog boxes, which also have the advantage of being able to use keyboard shortcuts (Enter or Esc for OK/Cancel, Y or N for Yes/No). 

* **Set Start Frame for Background Video:** If you use a video for a 3D View Background Image, you can set which frame of the project where the video begins playing. To set the keyframe, adjust the "Y" parameter to choose which Blender frame where the video should start playing. Because this uses an existing parameter, you no longer have the ability to move the video up or down, but I never used that feature and felt it was important enough to save the starting frame for the background video with the .blend file without altering the file format.

* **Delete Parent Deletes All Children:** If you delete a parent object, all children (whether they are selectable or not) underneath the parent are automatically deleted. This prevents the default Blender behavior where deleting a parent object suddenly scatters all of the child elements to their alphabetical place in the Outliner, making it difficult to determine if you actually removed everything under a parent object.

* **Duplicate Object Duplicates All Children:** If you press Shift+D to duplicate a parent object, all child objects are automatically duplicated as well. This prevents you from having to remember to select a parent then select all child objects and THEN run the duplicate command.

* **Linking a Parent Object to Another Scene Selects All Children Before Linking:** If you link a parent object to another scene, all child objects are automatically linked as well. This prevents you from having to remember to select a parent then select all child objects and THEN run the link command.

* **Outliner Has Case-Insensitive Sort:** It no longer matters whether an object name has uppercase or lowercase letters; the Outliner now sorts names in a case-insensitive manner.

* **Menus Should Only be at the Top of a Window:** From a usability perspective, menus should always be in a consistent place. I've eliminated the ability to put a menu at the bottom of a window, as it makes things unnecessarily confusing.

* **Obnoxious Keyframe Insertion:** If the Automatic Keyframe Insertion button is in the "on" state, the cursor line in the Dope Sheet turns an obnoxious red color (or whatever color the X axis in the 3D View is). This feature makes it obvious if you have Automatic Keyframe Insertion turned on so you don't accidentally write keyframes.

* **Parent Toggle Changes Children:** In the original Blender, if you toggle the visible/select/render icon in the Outliner on a parent object, only that parent is affected -- you need to hold down the Ctrl key to affect all of the children in the same way. This feature reverses that functionality for (at least for me) the more typical use case, which is, if I change something with a parent object, most likely the children need to be changed too. So toggling the visible/select/render icon in the Outliner on a parent object will affect all of the children in the same way. Holding down the Ctrl key will isolate the toggle to just the parent object.

* **Insert Recursive Keyframes:** Instead of being able to only right-click on one visible/select/render icon in the Outliner window and choose "Insert/Replace/Delete Keyframe", there are now additional menu options: "Insert Recursive Keyframes", "Replace Recursive Keyframes", and "Delete Recursive Keyframes". This allows you to set a keyframe for a visible/select/render icon on a parent plus all child objects.

* **New Lights are prefaces with "Light - ":** I like keeping all of the lights alphabetically together in the Outliner, hence the new prefix.

* **Left Click Animation Cursor:** If you prefer to use left-click to select as I do, this messes up the Dope Sheet mouse clicking, which then works the opposite as expected. With this fork, you are able to left click in the Dope Sheet to relocate the cursor to a new frame.

* **Forbid Menu Collapsing:** I never liked Blender's "Collapse Menus" feature. If a window is supposed to show a menu, I believe the menu should always be shown; there shouldn't be the extra step of unhiding a menu in someone else's Blender file. So this feature has been eliminated.

* **Properties Window Should Always Be Vertical:** Given what is in the Properties window and how it is organized, there is no good reason to show this window in a horizontal alignment. So this window now always has a vertical alignment.

If you want some -- but not all -- of these features in your own personal fork of Blender, you're in luck. Do a search in the code for "BETTER BLENDER BEGIN" for all of the spots where I changed the code. You should be able to easily discern where the code has changed for each feature and copy-and-paste the relevant bits into your own fork.

Enjoy!