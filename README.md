
![CC Graphics 2024_BarCharts](https://github.com/csae-coders-corner/How-to-make-bar-charts-of-impacts-with-standard-errors/assets/148211163/e6ac516a-d6a5-4afe-ad8d-442924a51d26)

# How-to-make-bar-charts-of-impacts-with-standard-errors
Previously creating a bar chart with standard error bars was a multistep process requiring you to create the standard error range yourself and overlay two charts on top of each other. The command cibar makes this process simple. 
Let’s say we want to plot a graph of impacts by two treatment groups. cibar takes the following syntax: 

	`cibar y, over1(treatment)`

And produces an output like this: 

![3a](https://github.com/csae-coders-corner/How-to-make-bar-charts-of-impacts-with-standard-errors/assets/148211163/e8c153cb-ed93-49dc-a3a0-bd8991996500)


You can easily add the usual twoway graph options using the syntax: 
`cibar y, over1(treatment) graphopts(twoway graph options)`

For example: 
```
	cibar y, over1(treatment) ///
graphopts( legend( order(1 "Control" 2 "Treatment")) ///
xtitle("") ytitle("Mean Y") ///
title("Treatment effects on Y") ///
subtitle("Mean and 95% confidence interval"))
```

Which produces:

![3b](https://github.com/csae-coders-corner/How-to-make-bar-charts-of-impacts-with-standard-errors/assets/148211163/d6888651-a403-4f29-9cec-26c893a48b23)


cibar also has the capability to show bar charts over multiple different groups using the options over2(group2), over3(group3) etc:

```
cibar y, over1(treatment) over2(female) ///
graphopts( legend( order(1 "Control" 2 "Treatment")) ///
xtitle("") ytitle("Mean Y") ///
title("Treatment effects on Y") ///
subtitle("Mean and 95% confidence interval"))
```

To produce something like this:

![3c](https://github.com/csae-coders-corner/How-to-make-bar-charts-of-impacts-with-standard-errors/assets/148211163/0642a8c8-3559-4142-8f2e-ed7bd001d9f0)

The command also has a range of capabilities to choose exactly how the bars, labels and legend look, so you can customise the chart to precisely your taste. 

AUTHOR: Emma Riley, University of Michigan (former DPhil candidate in the Department of Economics, Oxford)

28.01.2019
