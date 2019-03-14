# AlertController

### Basic - Summary

```swift
// Variable to store the textfield data
var textField = UITextField()

// Create the alert
let alert = UIAlertController(title: "Add New Todoey Item", message: "", preferredStyle: .alert)

// Defining the action to the alert
let action = UIAlertAction(title: "Add Item", style: .default) { (action) in
            // This will happen once the user clicks the "add item" button
}

// Add a textfield to the alert
alert.addTextField { (alertTextField) in
            alertTextField.placeholder = "Add item here"
            textField = alertTextField
}

// Add the action to the alert
alert.addAction(action)
  
// Present the alert
present(alert, animated: true, completion: nil)

```


### Example - Structure

When a button is pressed an alert appears and the user can add a new String to an array diplayed in a tableView.

```swift
@IBAction func addNewItem(_ sender: UIBarButtonItem) {
        
        var textField = UITextField()
        
        let alert = UIAlertController(title: "Add New Todoey Item", message: "", preferredStyle: .alert)
        
        let action = UIAlertAction(title: "Add Item", style: .default) { (action) in
            // This will happen once the user clicks the "add item" button
            
            // Add textfield input to the itemArray variable if the user wrote something in the textfield
            if textField.text! != ""{
                self.itemArray.append(textField.text!)
                self.tableView.reloadData()
            }
        }
        
        alert.addTextField { (alertTextField) in
            alertTextField.placeholder = "Add item here"
            textField = alertTextField
        }
        
        alert.addAction(action)
        
        present(alert, animated: true, completion: nil)
    }
```
