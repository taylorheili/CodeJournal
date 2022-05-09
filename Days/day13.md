#What i learned

Today we worked on reading plists with our zoo app. Fist step is to build your structure.
\\\swift
struct Exhibit: Codable {
    var Building:String
    var Latitude:Double
    let Longitude:Double
    var Animal:String
    var AnimalEmoji:String
    var Information:String
}
\\\
Next we did our URL bundle, decoder, and the do catch in the DataReader file.
\\\swift

struct DataReader{
    static func getPlistData()->[Exhibit]{
        let url = Bundle.main.url(forResource: "ZooExhibits", withExtension: "plist")!
        do{
            let data = try Data(contentsOf: url)
            let propertyListDecoder = PropertyListDecoder()
            let result = try propertyListDecoder.decode([Exhibit].self, from: data)
            return result
        }catch{
            print(error.localizedDescription)
            return []
        }
    }
}
\\\
Then finally we went to the control view and did our on appear so our data was printed to the console.
\\\swift
struct ContentView: View {
    var body: some View {
        VStack {
            Text("Hello, world!")
                .padding()
        }.onAppear(){
            let result = DataReader.getPlistData()
            print(result)
        }
    }
}
\\\
