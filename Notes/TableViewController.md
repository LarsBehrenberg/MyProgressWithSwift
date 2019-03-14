# TableViewController

### Basic - Summary
```swift
import UIKit

// Inherit class UITableViewController to be able to call TableView methods !
class TodoListViewController: UITableViewController{

 var itemArray = ["xxx","xxx","xxx"]

//MARK - Inserting data in tableView
    
    // Setting the number of rows needed in the tableView to the count of items in the array displayed
    override func tableView(_ tableView: UITableView, numberOfRowsInSection section: Int) -> Int {
        return itemArray.count
    }

    // Fill cells in tableView with items from itemArray and return each cell to the tableViewController
    override func tableView(_ tableView: UITableView, cellForRowAt indexPath: IndexPath) -> UITableViewCell {
        // Ask for a cell of the appropriate type.
        let cell = tableView.dequeueReusableCell(withIdentifier: "ToDoItemCell", for: indexPath)
        
        // Configure the cell’s contents with the row and section number.
        cell.textLabel!.text = itemArray[indexPath.row]
        return cell
    }

}

```

### Example - Structure

```swift

import UIKit

// Inherit class UITableViewController to be able to call TableView methods !
class TodoListViewController: UITableViewController{
    
    var itemArray = ["Find Mike","Buy Eggos","Destory Demogorogn"]

    override func viewDidLoad() {
        super.viewDidLoad()
        // Do any additional setup after loading the view, typically from a nib.
    }
    
    
    //MARK - Inserting data in tableView
    
    // Setting the number of rows needed in the tableView to the count of items in the array displayed
    override func tableView(_ tableView: UITableView, numberOfRowsInSection section: Int) -> Int {
        return itemArray.count
    }

    // Fill cells in tableView with items from itemArray and return each cell to the tableViewController
    override func tableView(_ tableView: UITableView, cellForRowAt indexPath: IndexPath) -> UITableViewCell {
        // Ask for a cell of the appropriate type.
        let cell = tableView.dequeueReusableCell(withIdentifier: "ToDoItemCell", for: indexPath)
        
        // Configure the cell’s contents with the row and section number.
        cell.textLabel!.text = itemArray[indexPath.row]
        return cell
    }
    
    
    
    
    //MARK - TableView Delegate Methods
    
    // What happens if the user selected one of the cells in the tableView
    override func tableView(_ tableView: UITableView, didSelectRowAt indexPath: IndexPath) {
        
        // Adding a checkmark to the item
        if tableView.cellForRow(at: indexPath)?.accessoryType == .checkmark {
            tableView.cellForRow(at: indexPath)?.accessoryType = .none
        } else {
            tableView.cellForRow(at: indexPath)?.accessoryType = .checkmark
        }
        
        // Prevents row from being selected by deselecting directly after selecting it
        tableView.deselectRow(at: indexPath, animated: true)
        
    }
}
```
