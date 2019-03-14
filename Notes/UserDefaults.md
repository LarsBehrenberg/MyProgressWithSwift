# UserDefaults

UserDefaults can be an easy and handy way to save small bits of data. Even arrays (see "playerQuestionsFinished") can get out of hands and become too big. If that's the case the time to load the app will become too long.

### Basic - Structure

```swift
import UIKit

let defaults = UserDefaults.standard

defaults.set(value: <Any>, forKey: <String>)

let data = defaults.<Any>(forKey: <String>)

print(data)
```


### Basic - Example

```swift
import UIKit

let defaults = UserDefaults.standard


// Bad practice to hard code key names -> More practicable to have the key in a constant to be able to change them easily
defaults.set(0.24, forKey: "Volume")
defaults.set(true, forKey: "MusicOn")
defaults.set(Date(), forKey: "AppLastOpened") // Sets current date/time

// Bad practice
let volume = defaults.float(forKey: "Volume")
let musicOn = defaults.bool(forKey: "MusicOn")
let appLastOpened = defaults.object(forKey: "AppLastOpened")


// Good practice
let playerNameKey = "PlayerName"
let playerQuestionsFinishedKey = "PlayerFinishedQuestionsArray"

let array = [1,2,3]
defaults.set(array, forKey: playerQuestionsFinishedKey)
defaults.set("YourName", forKey: playerNameKey)

let playerName = defaults.string(forKey: playerNameKey)
let playerQuestionsFinished = defaults.array(forKey: playerQuestionsFinishedKey)

```
