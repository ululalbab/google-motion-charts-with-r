# Combing charts with gvisMerge #
The function `gvisMerge` takes two `gvis`-objects
and merges the underlying components into one page. The charts are
aligned either horizontally or vertically next to each other in an HTML table.

The output of `gvisMerge` is a `gvis`-object again.
This allows us to apply the same function iteratively to create more complex
chart layouts.  The following example, aligns a geo chart
and table below each other, and combines the output with a motion chart to the right:
```
G <- gvisGeoChart(Exports, "Country", "Profit",  options=list(width=210, height=100))
T <- gvisTable(Exports, options=list(width=210, height=270))
GT <- gvisMerge(G,T, horizontal=FALSE) 
M <- gvisMotionChart(Fruits, "Fruit", "Year",
                     options=list(width=410, height=370))

GTM <- gvisMerge(GT, M, horizontal=TRUE,
                     tableOptions="bgcolor=\"#CCCCCC\" cellspacing=10")
plot(GTM)
```
&lt;wiki:gadget url="https://docs.google.com/uc?id=0By35Mtg9R9\_RYWRmNTIxYTYtYjIwOS00Zjk3LTljMmItYjNjNTEwZjU5NTJh&export=download&hl=en\_GB" width="800" height="500" border="0"/&gt;