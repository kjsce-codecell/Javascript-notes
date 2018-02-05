<h1 align="center"> Pop-up Boxes</h1>

>JavaScript offers three types of popup boxes, the **Alert**, **Prompt**, and **Confirm** boxes.

### Alert Box

>An alert box is used when you want to ensure that information gets through to the user.
When an alert box pops up, the user must click **OK** to proceed.
The alert function takes a _single parameter_, which is the text displayed in the popup box.

**Example**

```
alert("Do you really want to leave this page?");
```

### Prompt Box

>A prompt box is often used to have the user input a value before entering a page.
When a prompt box pops up, the user will have to click either OK or Cancel to proceed after entering the input value.
If the user clicks OK, the box returns the input value. If the user clicks Cancel, the box returns null.

>The prompt() method takes two parameters.
- The first is the label, which you want to display in the text box.
- The second is a default string to display in the text box (optional).

**Example**

```
var user = prompt("Please enter your name");
alert(user);
```

### Confirm Box

>A confirm box is often used to have the user verify or accept something.
When a confirm box pops up, the user must click either OK or Cancel to proceed.
If the user clicks OK, the box returns true. If the user clicks Cancel, the box returns false.

**Example**

```
var result = confirm("Do you really want to leave this page?");
if (result == true) {
  alert("Thanks for visiting");
}
else {
  alert("Thanks for staying with us");
}
```
