The structure of lists, in [[Lisp]], is important, because it dovetails perfectly with recursion.
    With recursion, we can process a collection, with a function definition, that operates on the head element of a list, and calls itself on the rest of the list.

```clojure
(def rec-fun (fn [l]
	       (if (empty? l)
		 ;; base-case
		 (accumulate
		  (do-something (first l))
		  (rec-fun (rest l)))))) 
```

This is the general pattern of a recursion function: we have our base case, which will kick us out of our recursive loop to avoid an infinite loop, and then we're going to accumulate our result. We want to perform some operation on an element of our collection, and then initiate a recursive call, on the rest of our collection.
## A Look At Recursion:
<img src="https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2F0xLEDEV-HQ%2F_BUjhutnjJ.png?alt=media&token=21142b4b-dece-442c-8e90-46ac3782b709" alt="drawing" style="width:50%;height:50%;"/>

> Visualizing the tree structure of a recursive function is a very powerful way to make sense of it. Generally, within [[Linguistics]], these are referred to as __derivation trees__, or __parse trees.__
> This can be considered the __procedural view__, however the declarative view is powerful as well:
We say a recursive function is __defined by contract__, with this definition being separated into two parts, with their respective behaviors defined.
         A base case determines the output behavior strictly in terms of the input.
         The inductive cases, assumes that the function is properly defined for smaller inputs, and defines the relationship between those inputs, and the full input.
