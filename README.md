

I made a tutorial on how to create this here (https://www.youtube.com/watch?v=OdbTsDc3pC8) explaining how to create those macros. The `.uasset` in here isn't the same as the tutorial but it was made using the same technique and is used in my game IDIOTIC THE GAME (https://store.steampowered.com/app/1746520/).


# How To Use

* Download or clone the file
* Copy the `.uasset` file inside called KeyRebinding_Widget.uasset
* Paste it inside your project's content file
* In `project settings/input` add your action and axis mappings and name them
* Inside the widget, add or edit an InputKeySelector and add an On Key Selected event



## For Action Mapping

* Connect to the event we added to the widget the macro `Action Rebinding` 
* The `Selected Key` output should be connected to `Input Chord`
* In `In Action Name` paste the name of the mapping you want to edit from `project settings/input` you made in the third step (It has to be the exact same name otherwise it won't work)
* Set `Reset Key?` to false
* The `Default Key` input shouldn't matter at this stage if `Reset Key?` is false, but I recommend setting it to none here jsut in case


## For Axis Mapping

* Connect to the event we added to the widget the macro `Axis Rebinding`
* The `Selected Key` output should be connected to `Input Chord`
* The `Scale` value should be either 1.0 or -1.0, depending on the axis you want to edit. (there should be 2 events & nodes for each axis mapping with the same name - see examples in file)
* Set `Reset Key?` to False
* The `Default Key` input shouldn't matter at this stage if `Reset Key?` is false, but I recommend setting it to none here jsut in case


## To Reset Key Mappings

* Add to the `On Clicked (Button_Reset)` event either `Action Mapping` or `Axis Mapping` node
* Set the name of the mapping you want ot reset in `In Axis Name`
* Set `Reset Key?` to True
* Set the default Key to whatever you want the default key to be
IF YOURE RESETTING AXIS MAPPING:
* Connect to `Input Chord` the variable `Selected Key` (it's an empty value but UE just throws errors if this isn't connected. Feel Free to fix it and lmk how if you can)
* Set the scale to either 1.0 or -1.0 depending on which mapping value you want to edit

## To Make The Buttons Show The Current Key Mapping

* Add to `Event Construct` and `Update button names` the macro `Get & Set Action Name`
* Connect the reference of the `Input Key Selector` of your choosing to the `self` input
* Set the `In Action Name` input to the exact same name as the mapping related to the `Input Key Selector`
* ???
* Profit


NOTE: this was made using UE5 from source. It works on UE 5.0.3 (and should for future builds too) but I'm unsure whether or not it'll work on UE4 versions. If you are using UE4 please refer to my tutorial (https://www.youtube.com/watch?v=OdbTsDc3pC8) how to make this widget instead as the concept and syntax should be the same.
