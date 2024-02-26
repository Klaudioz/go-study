# Deck of Cards Management System

## Overview
This program is a simple card deck management system written in Go. It allows the user to create a new deck of cards, print the deck, shuffle the deck, deal a hand from the deck, save the deck to a file, and load a deck from a file.

## Features

### `newDeck`
- Creates a new ordered deck of playing cards.
- The deck is an array of strings, where each string represents a card.
- The standard deck includes cards from four suits: Spades, Diamonds, Hearts, and Clubs.
- The values included in this implementation are Ace, Two, Three, and Four.

### `print`
- Outputs the contents of the deck to the console.
- Each card is printed on a new line with its index in the deck.

### `shuffle`
- Randomizes the order of the cards in the deck.
- Utilizes a random number generator seeded with the current time to ensure a unique shuffle each time.

### `deal`
- Splits the deck into two: a hand of a specified size and the remaining deck.
- The `handSize` parameter determines the number of cards in the hand.

### `saveToFile`
- Saves the current state of the deck to a local file.
- The deck is converted to a string and written to the file as comma-separated values.

### `newDeckFromFile`
- Loads a deck from a local file.
- The file contents are expected to be in the format produced by `saveToFile`.

## Usage

### Creating a new deck
```go
cards := newDeck()
```

### Printing the deck
```go
cards.print()
```

### Shuffling the deck
```go
cards.shuffle()
```

### Dealing a hand
```go
hand, remainingDeck := deal(cards, handSize)
```

### Saving a deck to file
```go
cards.saveToFile("my_deck.txt")
```

### Loading a deck from file
```go
cards := newDeckFromFile("my_deck.txt")
```

## Testing

### `TestNewDeck`
- Confirms that a new deck has the correct number of cards.
- Checks the first and last cards to ensure proper order.

### `TestSaveToDeckAndNewDeckFromFile`
- Tests the saving and loading of a deck to and from a file.
- Ensures that the deck maintains the correct order and number of cards after being saved to and loaded from a file.

### Running tests
To run the tests for this program, navigate to the directory containing the `deck_test.go` file and run:
```bash
go test
```