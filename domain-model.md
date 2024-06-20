# Domain Model

## Entities

- `Customer`
- `Restaurant`
- `RestaurantCategory`
- `Review`
- `MenuItem`
- `MenuItemCategory`
- `MenuItemOption`
- `ShoppingCart`

## Attributes and Operations

### `Customer`

- ID: string
- Name: string
- Email: string
- Address: string
- `addToFavorites(Restaurant.ID)`
- `addToCart(MenuItem.ID, MenuItemOption[])`

### `Restaurant`

- ID: string
- Name: string
- Description: string
- Logo URL: string
- Address: string
- Categories: RestaurantCategory[]
- Delivery Fee: number
- Delivery Time: [number, number]
- Offers Delivery: boolean
- Offers Pickup: boolean
- Offers Group Orders: boolean
- Business Hours: [date, date]
- Rating: number
- Reviews: Review[]
- Menu Items: MenuItem[]
- `searchMenuItems(string)`

### `RestaurantCategory`

- ID: string
- Name: string

### `Review`

- ID: string
- Rating: number
- Customer ID: string
- Date: date
- Comment: string

### `MenuItem`

- ID: string
- Name: string
- Description: string
- Price: number
- Customer Likes: number
- Categories: MenuItemCategory[]
- Options: MenuItemOption[]

### `MenuItemCategory`

- ID: string
- Name: string

### `MenuItemOption`

- ID: string
- Name: string
- Price: number
- Is Popular: boolean

### `ShoppingCart`

- Restaurant ID: string
- Items: [MenuItem, number][]
- Subtotal: number

## Class Diagram

![Class Diagram](./Class%20Diagram.png)
