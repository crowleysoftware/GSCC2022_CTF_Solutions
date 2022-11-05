# I'll Take that as a Complement

### Challenge
> You must be a bit wise to solve this: 
> 
> 10010010 10011110 10001101 10011010 10001100 11010010 10011010 10011110 10001011 11010010 10010000 10011110 10001011 10001100 

Here you are shown a series of binary numbers. They are each 8 bits so you can surmise they represent bytes. If you were to directly convert these as UTF-8 encoded letters you wouldn't have the solution that you're looking for:

|binary|decimal|letter|
|----------|----------|----------|
|10010010|146|&rsquo;|
|10011110|158|ž|
|10001101|141||
|10011010|154|&scaron;|
|10001100|140|Œ|
|11010010|210|ˆ|
|10011010|154|&scaron;|
|10011110|158|ž|
|10001011|139|‹|
|11010010|210|Ò|
|10010000|144||
|10011110|158|ž|
|10001011|139|‹|
|10001100|140|Œ| 

The clues are in the title and description. "Complement" is different than "compliment". And when I use the phrase "bit wise", I mean bit-wise complement. To take the complement of a bit you simply reverse it. If it is a 1 then the complement is 0, and vice-versa.

So taking the bit-wise complement of the bytes you arrive at:

|complement| |binary|decimal|letter|
|----------|----------|----|----------|----------|
|10010010|->|01101101|109|m|
|10011110|->|01100001|97|a|
|10001101|->|01110010|114|r|
|10011010|->|01100101|101|e|
|10001100|->|01110011|115|s|
|11010010|->|00101101|45|-|
|10011010|->|01100101|101|e|
|10011110|->|01100001|97|a|
|10001011|->|01110100|116|t|
|11010010|->|00101101|45|-|
|10010000|->|01101111|111|o|
|10011110|->|01100001|97|a|
|10001011|->|01110100|116|t|
|10001100|->|01110011|115|s| 