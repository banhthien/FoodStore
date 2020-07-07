# How to run the app

Open `FoodStore/FoodStore.xcworkspace`, and `Run (Cmd + R)`.

# Project structures
```
Messenger
├── Resources
├── Models
├── Modules
├── Core
│  └── Image
│  └── Persistence
│  └── Helper
|  └── Extensions
|  └── Networking
│  └── BaseVIPER
|     └── Presenter
|     └── Router
|     └── View

MessengerTests
```

### VIPER
[VIPER](https://medium.com/@smalam119/viper-design-pattern-for-ios-application-development-7a9703902af6) is a very clean architecture. It isolates each module from others. So changing or fixing bugs are very easy as you only have to update a specific module. Also for having modular approach VIPER creates a very good environment for unit testing.
###### Other Key Advantages of VIPER Architecture:
- Good for large teams.
- Makes it scalable. Enable developers to simultaneously work on it as seamlessly as possible.
- Makes it easy to add new features.
- Makes it easy to write automated tests since your UI logic is separated from the business logic.
- Makes it easier to track issues via crash reports due to the Single Responsibility Principle.
- Makes the source code cleaner, more compact, and reusable.
- Reduces the number of conflicts within the development team.
- Applies SOLID principles.
- Reduces the number of merge conflicts.

#### VIPER Template
I created a VIPER Xcode template to make the work easier, reduce time for create new files and repeate the same code per module.

To create new module: `Create new Group as your module name ---> Add new File --> Scroll down to select VIPER template --> type your module name.`

### BaseNetworking
A very lightweight URLSession wrapper to work with REST APIs. Easy to use and flexible with diffirent endpoints, methods.

```swift
networkClient.fetch(endPoint: ListUsersEndpoint.fetchListUser(lastId: lastId), type: [User].self) { (result) in
            switch result {
            case .success(let users):
                print("Fetched list users: \(users)")
            case .failure(let error):
                print("Error: \(error)")
            }
        }
```

