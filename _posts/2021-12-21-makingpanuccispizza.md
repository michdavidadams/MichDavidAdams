---
layout: post
title:  "Making Panucci's Pizza"
author: Michael
tag: apps
---

### My Intro to Software Engineering class had a pizza project.

We've only taken 2 previous classes involving programming, and they were both beginner Java classes. I've done some SwiftUI before and decided to just use that to make the app because it is what I felt most comfortable using. It took me a week or two to build a pretty rough app.
![Login First](/assets/shortcuts/panuccispizza/loginfirst.jpeg)
![Menu First](/assets/shortcuts/panuccispizza/menufirst.jpeg)

Playing around with the UI was the fun and easier part. I mostly struggled with the Pizza, Drinks, and Sides structs. They were all pretty similar:
```
public struct Pizza: Identifiable {
    let name: String
    let price: Int
    let description: String
    let image: String
    public let id = UUID()
    
}
```
And for the menu data, I just created arrays of each food struct:
```
let allPizzas = [
    Pizza(name: "Cheese Pizza", price: 6, description: "Our signature three-cheese pizza. Perfect for picky eaters, children's parties, and people who enjoy vanilla ice cream.", image: "front-view-pizza-with-cheese-brown-round-wooden-desk-dark-surface"),
    Pizza(name: "Veggie Lover's Pizza", price: 7, description: "A must-have for people too sophisticated for bland cheese pizza. Instead, sink your teeth into the delectable slimy olives with the mushy tomatoes.", image: "top-view-mixed-pizza-with-tomato-black-olive-melted-cheese"),
    Pizza(name: "Veggie Hater's Pizza", price: 7, description: "In the mood for something with lots of meat and no greens? Look no further!", image: "top-view-salami-pizza-with-cheese-pepperoni-wooden-table")
]
```
This worked fine just for presenting the data, but became problematic when I needed to store and edit the customer order. I started off just appending the name to a string and updating the total.
```
public class Order {
    var foodItem: String
    var orderTotal: Int
    var payWithCash: Bool
    var pickup: Bool
    public let id = UUID()
    
    init(foodItem: String, orderTotal: Int, payWithCash: Bool, pickup: Bool) {
        self.foodItem = foodItem
        self.orderTotal = orderTotal
        self.payWithCash = payWithCash
        self.pickup = pickup
    }
}
```
This was terrible. It really showed how sloppy my coding had been and was too difficult to edit and present in the checkout screen.

I instead tried making all food items (Pizza, Drinks, Sides) into 1 struct. I quickly realized my mistake, as there aren't different sizes for the sides. Instead, I created an OrderItem struct:
```
public struct OrderItem: Identifiable, Hashable {
    var type: FoodType
    var price: Int
    var details: String
    public let id = UUID()
}
```
Whenever a customer added an item to their order, it would create a new OrderItem. This also solved my issue with the custom pizzas. I could just make a string to present on the checkout screen instead of having to deal with different variables for different food types.

## Here's the final project.
![Login Final](/assets/shortcuts/panuccispizza/loginfinal.png)
![Custom pizza](/assets/shortcuts/panuccispizza/custompizza.png)
![Pizza](/assets/shortcuts/panuccispizza/pizza.png)
![Sides](/assets/shortcuts/panuccispizza/sides.png)
![Drinks](/assets/shortcuts/panuccispizza/drinks.png)
![Checkout](/assets/shortcuts/panuccispizza/checkout.png)
![Order submitted](/assets/shortcuts/panuccispizza/submitted.png)
![Attributions](/assets/shortcuts/panuccispizza/attributions.png)