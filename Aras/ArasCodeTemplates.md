# Aras Code Templates
<p class='editDate'>Created/Updated: 2021-10-14</p>

## Introduction
The "inline" coding in Aras is great for several reasons, but it has some drawbacks. When you want to write non-trivial code the "single"-method can easily get too long with to "much going on" to be readable. So I often use different templates/boiler plates to be able to write cleaner code.

## Simple Template
``` c#
        Init();
        // TODO: Write code

    } // End Main Method

    private Innovator Inn;

    private void Init() {
        Inn = this.getInnovator();
    }

} // End Main Class

class fin {
    void method() {


```