
#  PokemonCards App 

This app displayes cards of Pokemon , User can navigate to detials screen and can mark pokemon as favourite, App has 2nd tab that displayes list of favourite pokemons

## Installation guidelines 

 * Used Xcode 13.4 or above , 
 * SPM is used for dependency injection so app will build all dependencies, if it fail to add any dependency than you need to go to project setting and remove dependency and add it manually. 


## Architecture 

This App features are build using  Composable Architecture 

## State: A type that describes the data your feature needs to perform its logic and render its UI. like I have states viewAppeared, isLoading, isFavourite
 
## Action: A type that represents all of the actions that can happen in your feature, such as user actions, notifications, event sources, and more.

        enum CardsAction: Equatable {
          case retrieve
          case retrieveNextPageIfNeeded(currentItem: UUID)
          case cardsResponse(Result<Cards, ProviderError>)

          case retrieveFavorites
          case favoritesResponse(Result<[Card], Never>)

          case loadingActive(Bool)
          case loadingPageActive(Bool)

          case card(id: UUID, action: CardDetailAction)

          case onAppear
          case onDisappear
        }

## Environment: A type that holds any dependencies the feature needs, such as API clients, analytics clients, etc.
## Reducer: A function that describes how to evolve the current state of the app to the next state given an action. The reducer is also responsible for returning any effects that should be run, such as API requests, which can be done by returning an Effect value.
## Store: The runtime that actually drives your feature. You send all user actions to the store so that the store can run the reducer and effects, and you can observe state changes in the store so that you can update UI.

### Design Patterns

*  TCA (The Composable Architecture)
*  Publisher Subscriber  
*  State/ Binding.

## Testing.

* Unit Tests for Success and Failure situations. 

## Local storage

 * Core data is used to store favourite Pokemon details. 

## Localization 

* string files are implemented to support localization. 
 
## 3rd party framworks 

* swift-composable-architecture to support TCA 
https://github.com/pointfreeco/swift-composable-architecture
* KingFisher is used to download iamges
https://github.com/onevcat/Kingfisher.git 




