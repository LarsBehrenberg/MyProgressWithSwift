# NSCoder

### Example

```swift
class Item : Codable {

    var title = ""
    var done = false

}


var itemArray = [Item]()


func saveItems(){
    let encoder = PropertyListEncoder()
        
    do{
        let data = try encoder.encode(itemArray)
        try data.write(to: dataFilePath!)
    } catch {
        print("Error encoding item array, \(error)")
    }
        
    tableView.reloadData()
}
    
func loadItems(){
    if let data = try? Data(contentsOf: dataFilePath!) {
        let decoder = PropertyListDecoder()
        do{
            itemArray = try decoder.decode([Item].self, from: data)
        } catch {
            print("Error decoding item array, \(error)")
        }
    }
}
```
