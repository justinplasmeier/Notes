# n Days of Clojure

I'm learning Clojure. I'm also documenting the process through a series of incremental posts. I plan to spend at least one hour each day as often as possible on doing things with Clojure.

## day 0: 03/24/2017

I set up emacs with a bunch of cool plugins from [this GitHub repo.](https://github.com/flyingmachine/emacs-for-clojure)

## day 1: 03/25/2017

I watched two videos of Rich Hickey, the creator of Clojure, explaining the data structures of Clojure: [Clojure Data Structures Part 1](https://www.youtube.com/watch?v=ketJlzX-254) and [Part 2](https://www.youtube.com/watch?v=sp2Zv7KFQQ0). The speed (effectively constant time indexing) and immutability and persistance of the data structures is very impressive. I took notes: 

(link to git - Clojure Data Structures)

## day 2: 03/26/2017

I came up with an idea for a useful program to write in Clojure. I had been using `csvfilter`, a Python package to play around with a `.csv` file for a project. It was pretty slow, I assume, because Python is slow. So, that could be a cool idea for a first project. 

I read a bunch of [this Clojure tutorial](http://www.braveclojure.com/do-things) and took notes:

(link to git - Clojure Function Notes)

## day 3: 03/28/2017

I consolidated all of the relevant key bindings for emacs and paredit into a single place.

(link to git - Editor and Environment Notes)

## day 4: 03/31/2017

I spent some time messing around with the idea from day 2 to write a replacement for `csvfilter` in Clojure, and gave the project a name: Quip. My code eventually worked but only by consuming the entire file into memorty, which crashes for large files. I'm not really sure how to only take the lines that I need into memory while processing the entire file. 

If this is even possible, I think it would make the most sense to spend some more time familiarizing myself with Clojure in general before attempting to solve a problem without knowing what tools I have at my disposal.

## day 5: 05/04/2017

After a lengthy hiatus my free time is now in order again. I have decided to start over with reading [Clojure for the Brave and True](http://www.braveclojure.com/). I will continue to take notes and post them on Github. I'm going over the Emacs setup and key bindings as a refresher. 

## day 6: 05/05/2017

I'm resuming at the Emacs chapter. I have decided to not use Paredit until I'm more comfortable with Emacs. Next up is "Do Things: A Clojure Crash Course!" 

I went through the types and data structures. Next up is reviewing functions. This is slow going since I'm familiar with Scheme and remember most of these things. 

## day 7: 05/06/2017

Back to the grind of the basics. I read over my previous notes on functions and started getting into some of the features like `let`, `loop` and `recur`. 

## day 8: 05/10/2017

After a brief haitus due to finals, I'm back on Clojure, looking at the Hobbit symmetry example from Brave Clojure in more detail. I finished the "Do Things" chapter! 

## day 9: 05/12/2017

The topic _du jour_ is core functions like `map` and `reduce` and so forth. Once I wrap my head around the details of these, I think I will be ready to start practicing writing functions.   

I took a detour to modify the examples into something new. The function `funcmap` takes a list of function names, a list of functions, and a sequence. The output is a map where the keys are function names the values are the result of applying the corresponding function to the sequence:

```
(funcmap [sum avg count] ["sum" "avg" "count"] [1 2 3 4 5])
; => {"sum" 15, "avg" 3, "count" 5}
```

Implementation:

```
(defn keymap
	[name func nums]
	[name (func nums)])
	
(defn funcmap
	[names funcs nums]
	(into {} (map #(keymap %1 %2 nums) names funcs)))
```

There might be a better way to do this, but it's not bad.

## day 10: 05/13/2017

Today brings more notes on the core functions of Clojure. I worked through the rest of the section on Sequence Functions and Collection Functions. Next up are Function Functions!

## day 11: 05/15/2017

I decided to split up notes and examples. I finished the content of the Core Functions chapter in Brave Clojure and will be completing the example project next. 

## day 12: 05/16/2017

I spent some time reading the later chapters on concurrency and atoms/refs/etc. while on a bus, but I'm not really counting it since I didn't take notes or write code.

## day 13: 05/17/2017

I completed the vampire analysis example and a couple of the exercises. I definitely spent too much time confusing basic ways to process data before realizing that a simple `map` call was sufficient. In the future, I'll remember to start with the basic functions before introducing complexity in my solution. 

## day 14: 05/18/2017

I'm going to start the chapter on "Functional Programming" which should be a breeze since I just learned a lot about functional programming in my Programming Languages Course that I just finished. I finished the chapter but only by skimming the sections on the Peg game. 

## day 15: 05/19/2017

Rather than simply glossing over the peg game, I'm going to implement my own copy by manually copying code over. This will at least expose my conscious attention to the code, which will be better than a mere glossing over. I implemented the functions up to and including `connect`. 

## day 16: 05/22/2017

I'm continuing to go over the peg game. In some cases, for example the `connect-down-right` function, I will just read about what the function does and do my best to implement it myself. Given the unfamiliar (even compared to Scheme, as I've used Scheme) syntax, it has been tantamount to design first, code second. 

I'm picking up on some common patterns in these functions: 

* heavy use of `let` to bind names to variables 
* reduce with an anonymous function
* nested maps with `assoc-in`

I had a 5 hour long flight, so I managed to get almost all the way through! I just need to write the main function and make sure everything actually works. Going through this closely was definitely the right move- I understand when to use which functions better, and if nothing else, have built muscle memory for writing Clojure code. 

## day 17: 05/27/2017

After a brief hiatus to settle in at my internship, I have some time to continue on in Brave Clojure. Today, I will start Chapter 6: Organizing Your Project: A Librarian’s Tale. It's all about project organization which isn't the most intersting topic, but one of the most rewarding to spend time on getting right. 

I finished the first section on namespaces. Next up is "Real Project Organization."

## day 18: 05/29/2017

I finished taking notes on Project Organization. There's an example at the end of the chapter, "To Catch a Burglar" which I will start on next time. 

## day 19: 06/11/2017

It's been awhile. I'm staring a project written in Clojure currently called Zoia. It's an API for retreiving music from Google Drive for a music streaming client-side web application. However, before I continue I'm going to do the aforementioned example project from Brave Clojure. 