# No Clue

### Challenge
> Somewhere is a flag just waiting to be discovered

This challenge is a reconnaissance mission. You are given a link to documentation for an API that shows you the basics of how to play Tic Tac Toe over HTTP. You won't find a flag here, but at the bottom of the screen is another link to the Swagger documentation. If an API provides public documentation like this it can be very helpful for developers to understand how it works... and in turn it can be a treasure trove of information for bad actors. 

This particular API forgot to lock down some sensitive information. Take a look at the replay that demonstrations how the Admin configuration is wide open to the public and has flag just laying around:


![][def]

[def]: image/noclue.gif