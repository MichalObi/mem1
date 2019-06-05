Everything is changing fast. This situation is on 2019-04-06. Luciano Bestia  
Read the `Last projects` first:  
https://github.com/LucianoBestia/rust01_the_beginning  
https://github.com/LucianoBestia/rust02_workspace_and_testing  
# mem1
Learning to use Rust Wasm/WebAssembly with Dodrio Virtual Dom on a simple memory game for kids.  
The images are funny cartoon characters from the alphabet.  
The cards grid is only 4x4.  
You can play it here ( hosted on google cloud platform ):  
http://34.87.17.103/mem1/  
## Prepare the development environment (Windows)  
In my previous projects are the instructions how to install a basic Rust environment.  
For wasm workflow tool installation on Windows:  
https://rustwasm.github.io/wasm-pack/installer/  
You will need also a simple static file server:  
```
cargo install basic-http-server
```

## Source
Absolutely everything manually coded is in Rust language in the file `/src/lib.rs`.  
No manual JavaScript or HTML needed.  
The index.html file is a standard scaffold.  
The pkg/mem.js file is generated by wasm-bindgen.  
I prepared a small simple mem1.css with flex objects for styling.   
No need for npm or web-pack.  
The compiled files for the GitHub page are here  
(the game needs only a simple static file server):  
https://github.com/LucianoBestia/mem1_website  
You already know how to clone a GitHub repository:  
(in the rustprojects/ folder execute)  
```
clone git@github.com:LucianoBestia/mem1.git
```
## Build
Run in mem1/ folder
```
wasm-pack build --target no-modules
```
The warning for rand::Rng::shuffle will be solved in my second project. Ignore it.  
## Serve
Run the html server in mem1/ folder in a second terminal.
So it can continuously run while you incrementally build your changes in the first terminal.
```
basic-http-server
```
Open the default URI in your browser  
http://localhost:4000/  
## Cross-platform  
The web application can easily be converted into a cross-platform quasi native application with Electron for Desktops and PhoneGap for Mobile.  
The electron desktop application (Windows, MacOS, Linux) is here:  
https://github.com/LucianoBestia/mem1_electron  
The PhoneGap app (Android, iOS, WindowsPhone) is here:  
https://github.com/LucianoBestia/mem1_phonegap  

# Memory game rules
For the sake of simplicity, the first iteration is made as single player mode.  
The game starts with a grid of 8 randomly shuffled card pairs face down - 16 cards in all.  
The player flips over two cards with two clicks.  
If the cards do not match, the player starts a new turn with a click to turn both cards back face down. Then two clicks to flip over two cards.  
If the cards match, they are left face up and the player continues with the next turn. No additional third click needed in that case.  
The Count of clicks can be used as score. The lower the Count, the better score it is.  
![snap01](https://user-images.githubusercontent.com/31509965/55587238-181e8200-5755-11e9-88eb-f8fb62be581e.png)
# Next projects
The next iteration of this project is here:  
https://github.com/LucianoBestia/mem2  
# Programming references
https://doc.rust-lang.org/book/  
https://github.com/fitzgen/dodrio  
https://github.com/brson/basic-http-server    
https://rust-lang-nursery.github.io/rust-cookbook/    
https://github.com/anderejd/wasm-bindgen-minimal-example  
https://www.w3schools.com/w3css/  

Clarified the "rand" problem and solution for wasm-bindgen:  
https://medium.com/@rossharrison/generating-sudoku-boards-pt-3-rust-for-webassembly-85bd7294c34a  
In this book I didn't find a clear explanation for rand and wasm:  
https://rust-random.github.io/book/  

Images included free cartoon characters:  
https://vectorcharacters.net/alphabet-vectors/alphabet-cartoon-characters  

