# Environmental Sensor Data

## Introduction 
Environmental Sensor Data Collection Challenge. Continuously collect humidity samples every 5 seconds and display them using the lights on the micro:bit. 

## Step 1
Before you can use the environmental sensor, you must ``||gatorEnvironment: initialize||`` it

```blocks
gatorEnvironment.beginEnvironment()
```

## Step 1
``||basic: Continuously||`` ``||basic: show a number||``. 

```blocks
gatorEnvironment.beginEnvironment()
basic.forever(function () {
    basic.showNumber(0)
})
```

## Step 2
What ``||gatorEnvironment: number||`` do we want to be showing?  

```blocks
gatorEnvironment.beginEnvironment()
basic.forever(function () {
    basic.showNumber(gatorEnvironment.getMeasurement(measurementType.humidity))
})
```

## Step 3
We do not want a long list after the decimal point, so we ``||math: round||`` the ``||gatorEnvironment: humidity||`` to the closest whole number.

```blocks
gatorEnvironment.beginEnvironment()
basic.forever(function () {
  basic.showNumber(Math.round(gatorEnvironment.getMeasurement(measurementType.humidity)))

})
```

## Step 4
We need to ``||basic: take a break||`` for 5 seconds in between each measurement.

```blocks
gatorEnvironment.beginEnvironment()
basic.forever(function () {
    basic.showNumber(Math.round(gatorEnvironment.getMeasurement(measurementType.humidity)))
    basic.pause(5000)
})
```

## Step 6
``|Download|`` it and test it out. Once you have it working, click NEXT to move on to the next challenge

## Step 7
Now you will use the ``||radio: radio||`` to transfer ``||gatorEnvironment: carbon dioxide||`` data to the chromebook. The radio channel is labeled on your receiver micro:bit box. Set the data collecting micro:bit to the same group as the data receiving micro:bit.

Make sure you have the micro:bit on the right group.
```blocks
radio.setGroup(14)
gatorEnvironment.beginEnvironment()
```

## Step 8 
Now instead of showing the ``||gatorEnvironment: humidity||`` value on the micro:bit, ``||radio:send||`` the ``||gatorEnvironment: carbon dioxide||`` value over the radio instead.
```blocks
radio.setGroup(14)
gatorEnvironment.beginEnvironment()
basic.forever(function () {
    radio.sendNumber(Math.round(gatorEnvironment.getMeasurement(measurementType.eCO2)))
    basic.pause(5000)
})
```

## Step 9
``|Download|`` the code and test it out. 

```package
gatorEnvironment=github:sparkfun/pxt-gator-environment
```


