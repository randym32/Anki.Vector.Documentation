# How to add (or change) voice commands

This is an article describing how to add (or modify) a Voice command 
on the EscapePod.  It focuses on how to craft a small grammar 
and convert it into rule(s) for EscapePod.  (I hope to create a later
article explaining in more detail how to create behaviors that exist
on extensions to the Escape Pod.)

## A glossary of terms

Let's define some terms first to be clear and consistent within the article:

| Term     | Definition |
|----------|------------|
| behavior | A structure on Vector to represent and manage a potentially complex task that might involve animations, changing his emotions, path planing, driving, and so on.  It is also used on the EscapePod as a catchall for utterances and how they are made into an intent.|
| intent   | An intent is a structure with an internal code that is used to represent the how to respond to the phrases spoken by a person. It may represent the action requested, an answer to a query, or an action that emotionally responds to what was said.  |
|property name|The name of a key in the structure; also called a field.|
|structure |A table of property names (aka field, or key) and the value associated with it.|
|utterance |What a person said, and in the context of this article, the transcription to text of what the person said.|

## Planning

I'm going to focus on the idea of a new voice command, to give an idea of the
overall process.  After all, modifying an existing voice command is easier,
just a matter of winging it.  This may give some idea how to extend existing
commands.

We'll use 5 steps to create a voice command on the EscapePod:

1. Decide what you want Vector to do when he hears the voice command
2. Make a list of what you want to say
3. _Optional (or in rare cases)_ what extra information that Vector needs to know
4. Create a helper table, in preparation for entering it into the EscapePod
5. Plonk this into the EscapePod; the EscapePod UI is  still a bit new and very
   techy-focused in this area, so I'll try to explain what some of the fields do.

The first step is to decide what you want Vector to do, from the [list of
supported cloud intents][intents].  (For now let's ignore EscapePod extensions.)
It has to be one that Vector recognizes.
(See [here][intents] for a table of the intents Vector recognizes.)

For demonstration purposes I'm going to use **intent_imperative_eyecolor_extend**
(and pretend that it does not already have a voice command.)


### Making Table of What you can say

Making a list of what you want to say to Vector is the second easiest part.
Write the items down in a bullet-pointed list.  For the set eye color intent, 
the stock list of phrases that Vector recognizes include:

* change eyes
* change eye color
* make your eyes

Tip: stick with one to two words, occasionally three; try getting rid of common
articles (a, the, his), determiner (your) and other common words.  Go for "google
whacks" — where the word or word pair is not used in any other voice command.

Following this tip, we might change the last item to:

* make your eyes


### See if Vector needs extra information in the intent and creating a helper table

Next, look up in the cloud intents page to find if the intent needs extra
information.

There are three possiblities here

1. The cloud intent doesn't need any extra information (most cases)
   If this is the case, skip to the next section.
2. The cloud intent has a single property that it needs a value for;
   this property have a name, and fixed set of values that it accepts.
   (This happens for a handful of intents.)
3. The cloud intent takes a single property, but the value can be anything.
   This is used with the intent to teach Vector your name.


Following the eye color example, it takes one property, **eye_color**, that
says which color to shade the eyes.  This property only accepts very specific
values. Lets create a table of the property values to keep it organized.


| Property Value | Spoken phrases |
|--------|------------|
|COLOR_BLUE| |
|COLOR_GREEN||
|COLOR_ORANGE||
|COLOR_PURPLE||
|COLOR_TEAL||
|COLOR_YELLOW||


What we need to do now is add the  phrases that go with each possible value:

|Property Value| Spoken phrases|
|--------------|--------------|
|COLOR_BLUE|blue, azure, sapphire|
|COLOR_GREEN|green, lime|

etc.


Tip:  like earlier stick with one to two words, occasionally three; try getting
rid of common articles (a, the, his), determiner (your) and other common words.
And go for”google whacks” — where the word or word pair is only used here for a
color.


## Entering this into the EscapePod UI

Now we're ready.
Let's begin entering this into the EscapePod now.

1. First, Click on the menu in the upper right hand corner, and select "Behaviors":

    ![](EPMenuIntents.png#center)
    _Figure: Behaviors item on menu_

2. Next, Click on the pull down menu and slect "Add A Behavior"

    ![](EPDevMenuAddBehavior.png#center)
    _Figure: Add Behavior item on menu_

3. A popup will appear giving dire warings.  Just click ok.

    ![](EPDamnTheTorpedos.png#center)
    _Figure: Add Behavior item on menu_

4. Next you'll a place to start entering the information

    ![](EPIntentCreate1.png#center)
    _Figure: Starting to create a voice command_
    
    Leave the checkbox clear for now.
    Give it a nice name (it doesn't matter,
    and a helpful description (again it won't affect anything).

### Entering the Intent name and trigger phrases

Next fill in the intent name -- **intent_imperative_eyecolor_extend** --
in the field below the word "Behavior"

![](EPEnterIntentName.png#center)
_Figure: Enter the intent name_


Then take the list of words and phrases were made earlier -- e.g. "change eyes"
-- and combine them using commas to separate the phrases.  If the intent has
extra properties (like this one does), then add all of the
words and phrases for the  property values from the table made earlier;
separate with commas too.

Take this big, long list of words, and put it into the field below "Key Words".
(The field is small so I recommend combining the words into a list in 
your favorite text editor, then copy-pasting it to the field.)

![](EPEnterKeyWords.png#center)
_Figure: Enter the key words_

If you don't have any extra properties, then just click "Save" and you're
done.  If you do have properties, then we need to go to the next step:

### Entering the property names, and their phrases

To enter in the property names and their key words, we have to leap thru a few
extra hoops:

1. Check the box for “Check to enable developer options”

    ![](EPEnableDeveloperOptions.png#center)
    _Figure: Click it to enable devleper options_

2. Another popup will appear giving more dire warings.  Just click ok.

    ![](EPDamnTheTorpedos2.png#center)
    _Figure: Enabling developer options is... scary?_

3. Click “Add Extended Key”

    ![](EPAddExtendedKey.png#center)
    _Figure: Time to add the property names and values_

4. Enter the property name in the “Extended Key” entry.

    ![](EPExtendedKey.png#center)
    _Figure: Enter the property name_

Now let's go back to the table of property values and their phrases that we made
earlier. For each row in the table:

1. In the “Key Phrase” field, enter the property name (left column of the row
   in the table we made):

    ![](EPPropertyValue.png#center)
    _Figure: Enter the property value_

    For example:

    ![](EPPropertyValueEx.png#center)
    _Figure: An example the property value_


2. Add in the phrase that indicate this value .  Unlike the main list of phrases,
    we have to enter each of the phrases in here separately.  Enter the
    first key word or phrase into the "Parameter" field.

    ![](EPLotsOfPVKeywords.png#center)
    _Figure: One property value key phrase at time_

    Then click “Add Parameter” and repeat for the rest of the phrases
    for this property.
    
3. If there is are more rows in the table, click “Add Key Phrase”

Once you're done entering in the table, click "Save."

## Advanced Properties: Wild cards

Now that we've gotten used to the property name and values for intents, we can
go on to an advanced case.  Phrases can also capture whatever the person
actually said and send that text for the property value.

This is used in only one intent at present: Teaching Vector your name. Let's
look at it.  The list of phrases that trigger the intent are like any other
intent:

* my name is
* call me
* you may call me
* please call me


In this example **username** is the property name and will be filled in with
whatever the persons says after the phrases above.

### Entering this into the EscapePod UI

Here;s how to do it.  Go thru all of steps before.
And stop before clicking on "Add Extended Key".

1. Enter the property name in the field called "Extended Key" under "Parser":

    ![](EPWildcardKey.png#center)
    _Figure: Where the Wild Card property names grow.. erm, go_

    For example:

    ![](EPWildcardKeyEx.png#center)
    _Figure: Example of the **usename** wild card property name _

2. Then add in ```[INTENT_INVERSE]``` to the "Parser Target" field:

    ![](EPParserTarget.png#center)
    _Figure: Magic field values!_

Then click "Save" and you're done.


## Linking with the EscapePod

A voice command can be tagged to be sent to an EscapePod extension for
further processing.  The steps are the same as the above, except
modify these to work with EscapePod extensions:

1. Make up a fake intent name for the intent for your 
EscapePod extension to key off of.

2. Under the "Parser" section, check the "Enable External Parsing"
   option.

    ![](EPEnableExternal.png#center)
    _Figure: Check this to forward it to an EscapePod extension_

3. Click "Add Response Parameter" :

    ![](EPAddResponseParameter.png#center)
    _Figure: Check this to forward it to an EscapePod extension_

3. Enter "final_intent" into the "Parameter Key" field, and the name of the
   intent to use as a back up if the EscapePod can't contact the extension or
   doesn't get a result.  **intent_play_cantdo** is recommended, but you can
   use whatever you  want.

    ![](EPFinalIntent.png#center)
    _Figure: The intent name to use if the EscapePod extension doesn't work out_

Then click "Save" and you're done.


## Follow up
Note: someone can copy the table of intents to the forums wiki

Note: You can, in principal, have more than one property in your phrase pattern.
Including combining an enumerated property and a wild card, but I have
 not characterized how well tested that works or a use case where it’d feel
 natura.


I recommend changing the following in the EscapePod UI:

* “Extended Key” to “Parameter Name” (or at least something less confusing)
* (“Wildcard Key” is also a parameter, so renaming to “Wildcard Parameter Name”
   at the same time ould be more consistent)
* “Key Phrase” isn’t a phrase, it’s a very programmer specific thing. I
  recommend that it be changed to “Property Value”
* (“Parameter” isn’t a parameter at all, its key words or other utterance.
   Recommend changing it to “Key words”
* "Behavior" to a more correct term.  Leaving it as is will cause lots of
  confusion, frustration and hard to help people who being to work with the
  behavior tree and we have to spend half a dozen messages establishing
  which ambiguous thing they are working on.

[intents]: ../protocols/intents.md
[intents1]: https://wire.my.to/vectorwiki/site/protocols/intents.html
[intents2]: https://randym32.github.io/Anki.Vector.Documentation/protocols/intents.html


