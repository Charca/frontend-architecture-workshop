# Domain Model

## Entities

- `Customer`
- `Restaurant`
- `RestaurantCategory`
- `ShoppingCart`

## Attributes and Operations

### `Customer`

- ID: string
- Name: string
- Email: string
- `addToFavorites(Restaurant.ID)`

### `Restaurant`

- ID: string
- Name: string
- Description: string
- Logo URL: string
- Address: string
- `searchMenuItems(string)`
