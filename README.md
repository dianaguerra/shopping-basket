# Shopping Basket with Redux & Redux Toolkit

## Task Description

You are creating an e-commerce application and need to implement basket functionality in Redux.
Products can be added to and removed from the basket. If they already exist in the basket, their quantities should be modied accordingly –
increasing when adding a product again and decreasing when trying to remove a product.
The part responsible for layout - the basket component - is already done. Your task is to implement the Redux-related parts to ensure that
everything is working ne. The parts are: a basket reducer, actions and connecting a basket component with the Redux store.
Redux store and products

The Redux store has the following schema:

{ 
    "basket": { 
        "products": [] 
    }
}

Each product takes the following shape:

{ 
    "id": string, 
    "name": string, 
    "quantity": number, 
    "price": number, 
} 

The Redux store is created and connected with the reducer in the background.

## Actions

There are two action creators dened in the project: addProductToBasket and removeProductFromBasket.
addProductToBasket accepts product as a single parameter. product is an object of the shape described in the Redux store and
products section above. This action creator returns an action of the ADD_PRODUCT_TO_BASKET type.
removeProductFromBasket accepts productId as a single parameter. productId is a number, as described in the product object
denition above (product.id).
Your task here is to set the type of an action created by removeProductFromBasket to REMOVE_PRODUCT_FROM_BASKET.

## Basket reducer

The basket reducer should handle the two actions mentioned above (of the types: ADD_PRODUCT_TO_BASKET and
REMOVE_PRODUCT_FROM_BASKET).
The ADD_PRODUCT_TO_BASKET handler should behave in the following way:
if the product is added for the rst time, it should be added with a quantity equal to 1;
if the product already exists in the basket, its quantity should be increased by 1.
Similarly, REMOVE_PRODUCT_FROM_BASKET handler should be implemented so that:
if a product's quantity is equal to 1, it should be removed from the basket products list;
if a product's quantity is greater than 1, it should be decremented by 1.

## Basket component

The basket component is already implemented and working as expected. Your task is to connect it with the Redux store and pass three props: products, totalPrice and an onRemove handler:

products should be the list of products taken directly from the store;
totalPrice should be calculated based on the list of products;
onRemove is a handler accepting a productId parameter, and should dispatch the removeProductFromBasket action.

## Libraries

The project uses the following libraries:

react: 16.3.1,
react-redux: 7.2.0,
redux: 4.0.5.

## Usage

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in your browser.
