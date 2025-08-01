What is the `change` event, and how does it work?

The `change` event is a special event which is fired when the user modifies the value of certain input elements. More specifically:

- When a checkbox is ticked or unticked.
    
- When a radio button is ticked.
    
- When the user makes a selection from something like a date picker or dropdown menu.
    
- When an input loses focus (the user tabs to the next field, or clicks out of the form) after the user has changed the value.
    
- When the user otherwise confirms the value, such as by hitting enter after typing some text.
    

Note that the `change` event does NOT fire when your user types in an input. The `change` event will only fire after they have focused on another element.

The `change` event still generates an `Event` object, but unlike most other events it does not generate a custom implementation – the only properties and methods you will have access to are those on the base `Event` object.

This differs from the `input` event, which generates a dedicated `InputEvent` object. The change event also differs in a few ways. An `input` event WILL trigger when a user types content into a field, for example.

These differences are important to remember, as you might get tripped up by the timing of these events firing.