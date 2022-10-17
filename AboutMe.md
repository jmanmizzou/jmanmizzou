# Personal Information 

**Hello!** My name is Jackson Orr!

- I am from Columbia, Missouri 
- I am 20 years old 
- I have a twin sister

## Things That Interest Me

My favorite programing languange is *Python!* an example of that is:

```
import math

stopProgram = False

while not stopProgram:
    while True:
        try:
            wallSpace = float(input("Enter the square feet of wall space to be painted: "))
        except ValueError:
            print("Error: Please enter a numeric value.")
        else:
            if wallSpace <= 0:
                print("Please enter a value greater than zero.")
            else:
                print("")
                break

    while True:
        try:
            price = float(input("Enter the price of the paint per gallon: "))
        except ValueError:
            print("Error: Please enter a numeric value.")
        else:
            if price <= 0:
                print("Please enter a value greater than zero.")
            else:
                print("")
                break

    gallons = math.ceil(wallSpace / 350)
    hours = 6 * (wallSpace / 350.0)
    paintCost = gallons * price
    laborCost = hours * 62.25
    totalCost = paintCost + laborCost

    print("***ESTIMATE***")

    print("Number of gallons of paint needed:", gallons)
    print("Hours of labor needed: %.1f hrs" % hours)
    print("Cost of paint: $%.2f" % paintCost)
    print("Cost of labor: $%.2f" % laborCost)
    print("Total cost: $%.2f\n" % totalCost)

    if input("Would you like to do another estimate? (y / n) ") != "y":
        stopProgram = True
    else:
        print("")
```

I travel a lot! I've been to over 50 countries and counting! I hope to continue traveling as much as I can in my life. My goal is to vist every country in the World by the time I turn 50 years old!

Here is a photo of me skydiving in Interlaken, Switzerland!

![skydiving photo](https://user-images.githubusercontent.com/115883101/196229403-2562a706-7627-499b-a4f9-9b27af399df9.jpg)

If you'd like to learn more about the skydiving company that I jumped with in Switzerland, please [click here!](https://www.skydiveswitzerland.com/)

If you'd like to continue learning about me or go back to the [home page](ReadMe.md),
        



