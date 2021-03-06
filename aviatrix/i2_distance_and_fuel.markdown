# Aviatrix I2: Distance & Fuel

Right now our magical plane can fly around and around, never running out of fuel. Let's work on tracking how far we're going, how much fuel we're using, and build the ability to refuel.

## Tracking Distance Flown

When you read the gauges in `main.swift` you see something like this:

```
Reading the gauges...

| Running:   | ✅
| Location:  | St. Louis
| Fuel:      | 0 gallons
| Max Fuel:  | 0 gallons
| MPG:       | 0.4
| Fuel Bill: | $0.00
| Distance:  | 0 miles
```

That `Distance` line doesn't change even when we fly to other cities.

### In The Simulator

When you look in the `gauges` method of the simulator you see a line like this:

```
print("| Distance:  | \(plane.distanceTraveled) miles")
```

That tells us the distance is coming from the `distanceTraveled` function.

### `distanceTraveled`

In Aviatrix, `distanceTraveled` is an variable -- it's just a number that's stored, not a method that does calculations. Up at the top of the class, it gets set to `0` when the plane is first created.

But it never gets changed. What code can you add to the `flyTo` function so that it updates the value of `distanceTraveled`? Make sure that the values accumulate as you go from one city to another, _not_ resetting each time. Pay careful attention to the order of your instructions in `flyTo`!

#### Results

When it's working and you fly a plane from St. Louis to Denver, the gauges would say:

```
| Running:   | ✅
| Location:  | Denver
| Fuel:      | 0 gallons
| Max Fuel:  | 0 gallons
| MPG:       | 0.4
| Fuel Bill: | $0.00
| Distance:  | 768 miles
```

Then after flying back to St. Louis:

```
| Running:   | ✅
| Location:  | St. Louis
| Fuel:      | 0 gallons
| Max Fuel:  | 0 gallons
| MPG:       | 0.4
| Fuel Bill: | $0.00
| Distance:  | 1536 miles
```

#### Challenge

Starting in St. Louis, what's the closest you can get to flying 5000 miles without going over?

## Burning Fuel

It takes a lot of gasoline to move an airplane. Commercial flights loaded up with passengers can need five gallons of gas to go just one mile!

Let's build out the fuel-tracking in our project.

### In The Console

When you read the gauges in the console you see:

```
Reading the gauges...

| Running:   | ✅
| Location:  | St. Louis
| Fuel:      | 0 gallons
| Max Fuel:  | 0 gallons
| MPG:       | 0.4
| Fuel Bill: | $0.00
| Distance:  | 0 miles
```

### Max Fuel

*Can you modify the code in your Aviatrix so the Max Fuel shows up as 5000 gallons?*

When it works your gauges will show this:

```
Reading the gauges...

| Running:   | ✅
| Location:  | St. Louis
| Fuel:      | 5000 gallons
| Max Fuel:  | 5000 gallons
| MPG:       | 0.4
| Fuel Bill: | $0.00
| Distance:  | 0 miles
```

### Fuel to Fly

Let's track how much fuel we're using to fly:

* Your plane has a `milesPerGallon` attribute with the value `0.4`
* You know how far it is from one city to another
* Your fuel level is stored in the `fuelLevel` attribute.

*Can you modify your `flyTo` method so that it calculates how much fuel is used during the flight and decreases `fuelLevel` the right amount?*

When it's working correctly and you fly from St. Louis to Denver your gauges will say:

```
Reading the gauges...

| Running:   | ✅
| Location:  | Denver
| Fuel:      | 3080.00 gallons
| Max Fuel:  | 5000 gallons
| MPG:       | 0.4
| Fuel Bill: | $0.00
| Distance:  | 768 miles
```

#### Challenge

* What happens when you run out of fuel?
* Starting in St. Louis, what's the closest you can get to an empty gas tank without hitting zero?

#### Extra Challenge

Only try this if things are going really well.

Gas is heavy, so the more gas you're carrying the more energy it takes to move your plane and the lower your miles per gallon.

Instead of your MPG always being `0.4` can you modify your code so the MPG is approximated based on the number of gallons in the tank when the flight starts? Here's a formula for you:

```
mpg = 0.55 - (Number of Gallons)x(0.00005)
```

What's the different in the miles-per-gallon of a full tank versus when the tank is empty?

## Refueling

Each airport is happy to sell us jet fuel.

### In The Simulator

You can look at the `refuel` function in `main.swift` and you'll see:

```
let refuelData = plane.refuel()

print("Refueling...")
print("⛽ Here in _________, jet fuel costs _________")
print("⛽ You refueled _________ gallons totaling _________")
```

There are a lot of things happening in there!

### `refuel` - Iteration 0

Let's make sure these print statements actually print out complete sentences. Fill in those blanks with interpolated variables. You will need to pull in info from your `Aviatrix` class!

### `refuel` - First Try

First there's a call to the `refuel` function. Find that function in your Aviatrix.

*Can you write one line of code that fills the gas tank back to it's maximum level?*

Try it in your simulator. When you fly to another city, then refuel, is your gas tank full? Check the fuel level by reading the gauges.

### `refuel` - Doing Better

You can see from the simulator code that it's expecting to get back a dictionary with three key/value pairs:

* `quantity` referencing how many gallons were added
* `unit price` with the price per gallon in the current city
* `spent` with the total bill for this fill-up

*First: return a dictionary out of this function. The three keys are listed above.*
*Second: Can you improve your `refuel` method so that these three values are correctly calculated?*

Here are a couple tips:

* start by calculating how much gas you need
* find the price in the current city in `AviatrixData`
* the simulator will take care of rounding off the cents, so don't worry about that

### Tracking Total Fuel Costs

Eventually you'll have to pay that fuel bill. Let's keep track of our total spent on refueling.

Your plane has a `fuelCost` variable that starts at zero. Each time you refuel, add the amount that you spent to the total `fuelCost`. Read your gauges after two refuelings and make sure that the total is correct.

## What We've Got

* We can navigate between cities
* We track the fuel usage as we move city to city
* We can refuel in any city
* We track the total cost of refueling

## Challenges

* Try to visit each of the four cities we started with (St. Louis, Phoenix, Denver, and Salt Lake City). What's the *lowest possible fuel bill* to complete the trip without crashing?
* What's the most total miles you can travel with just one refueling?
