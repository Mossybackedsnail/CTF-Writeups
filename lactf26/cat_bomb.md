## mist/cat-bomb! -- burturt

I was hiking in the woods when I stumbled across this amazing thing: thousands of these orange structures! I stopped to take a photo but then this cat had to photo bomb my otherwise perfect photo with it's tail! Can you find where this photo was taken?

Move to the exact location where this photo was taken in Google Street View, and then submit the coordinates (latitude and longitude) from the url in the format ```lactf{LAT,LONG}```.

For example, if the photo [celebrating the anniversary of the Bruin Bear statue](https://alumni.ucla.edu/event/the-bruin-bear-statue-anniversary/) was the target photo, then [this](https://maps.app.goo.gl/YTt69MqjjUZAxVS58) would be the correct Google Street View location, and the answer to submit would be ```lactf{34.0710103,-118.4449715}```.

## Solution

There really isn't any trick to this one, it's just another OSINT challenge. The attached image depicts a cat tail under a tunnel of torii gates. It's been stripped of all metadata so that isn't an option

![](images/cat-bomb.jpeg)

Doing any sort of searching for torii gate tunnels will quickly lead to Fushimi Inari Shrine in Kyoto. I started by looking around on google street view towards the entrance of the shrine but the bottoms of the pedestals didn't match the one from the image so I moved on. The actual location of the image is further down the path closer to where the street view camera stops.

![](images/cat_bomb_1.png)

Simply move one step fowards on street view so you're lined up to where the photo was taken, copy the coordinates from the url and get the flag!

```lactf{34.9681588,135.7772502}```

---