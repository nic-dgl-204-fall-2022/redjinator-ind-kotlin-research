# Independent Kotlin overview research - part 1

## Kotlin for Data Science
After reading each article I decided Kotlin for Data Science was my favorite that I would like to explore further. Using Kotlin for Data Science is a great choice because Kotlin is easy to learn, locks in variable types, does not allow variable nulls by default unless specified during declaration which in turn makes code less prone to errors and easier to debug. Kotlin has the same advantages of Java for performance since it is also run on the Java Virtual Machine, and can also use pre-existing Java libraries that offer greater trust and stability through maturity.

## Key resources
1. I’ve chosen the following libraries as my “second” key resources because of the parallels in using pandas, NumPy, and matplotlib which I am somewhat familiar after using python to try and replicate some of my more successful technical analysis algorithms that I originally wrote in Pine script. I’m more comfortable using programming languages for analyzing data than for creating applications. I realize there is likely to be some functional overlap between the libraries listed below but I will have to play around and figure out is going to suit my needs as I transition to using Kotlin over python.
    
      a.  [Multik](https://github.com/Kotlin/multik): is a library for working with multidimensional arrays, providing convenience methods and more               efficient data structures. Can also be used with the Kotlin kernel for Jupyter.
      
      b. [Kotlin DataFrame](https://github.com/Kotlin/dataframe): Data frames using pandas was very beneficial for me, I haven’t read to much of the                documentation yet, but it seems to provide many of the same advantages as data frames in pandas (from my limited point of view). 
      
      c. [Kotlin-statistics](https://github.com/thomasnield/kotlin-statistics): Contains many functions that I remember having to code myself to use when       using Pine script v3 to look for patterns in candlestick chart data. 
      
      d. [Kmath](https://github.com/SciProgCentre/kmath): Intended to bring the benefits of working with NumPy to Kotlin, but much improved using Kotlin’s          superior features and flexibility.  This was a no-brainer for me, and I’m looking forward to seeing what it can do, and what advantages there are           over it’s spiritual predecessor.
      
      e. [lets-plot](https://github.com/JetBrains/lets-plot): An open source plotting library from Jet Brains for working with statistical data and is available on multiple platforms. 
      
      
2. Interactive editors: [Jupyter Notebook](https://jupyter.org/), [Datalore](http://jetbrains.com/datalore?_gl=1*lrzaxd*_ga*MTkyMzIwNDA0OC4xNjYzMzQ1MTYw*_ga_9J976DJZ68*MTY2MzQ2Nzk5MC43LjEuMTY2MzQ3MDU4OC42MC4wLjA.&_ga=2.42794466.631111152.1663345160-1923204048.1663345160), and [Apache Zeppelin](https://zeppelin.apache.org/) are mentioned. I use Jupyter notebooks often with python. I find Notebooks particularly helpful when learning programming concepts and being able to keep everything in notebook for reference is very convenient and one of the main tools I use to teach myself coding concepts and keep smaller snippets isolated less prone to getting lost in my unruly amount of files on my operating system.

3. [https://kotlinlang.org](https://kotlinlang.org/docs/basic-syntax.html): The sections under basics (basic syntax, Idioms, examples, coding conventions) are all well organized and concise which is perfect as a reference for a novice like myself.

4. [YouTube: Kotlin Tutorial by Navin Reddy](https://www.youtube.com/playlist?list=PLsyeobzWxl7rooJFZhc3qPLwVROovGCfh): The course is broken up into almost 50 videos with narrow topics so it’s easy to hone in on a concept that you want to look at. I find this useful for when I am having difficulty sitting and reading text on the computer screens for long periods of time.

5. [Codewars](https://www.codewars.com):Having a place to be given problems to solve without having to build an app allows practicing to be very focused. Being able to change the difficulty allows you to control how you practice. You can re-enforce fundamentals, practice at your level, or really challenge yourself with a difficult problem. I feel this used in the right way could be extremely valuable.

6. [JetBrains Academy Kotlin tracks](https://hyperskill.org/tracks?_ga=2.119806287.631111152.1663345160-1923204048.1663345160&_gl=1%2ag7jp6f%2a_ga%2aMTkyMzIwNDA0OC4xNjYzMzQ1MTYw%2a_ga_9J976DJZ68%2aMTY2MzQ3NTIwNS43LjAuMTY2MzQ3NTIwNS4wLjAuMA..&category=4): This one I haven’t explored much yet, but after searching a little online I found a decent amount of positive sentiment towards the tracks/courses. I figured I would mention it since it seems to be considered a valuable resource. 

## GitHub Repo Related to Kotlin for Data Science
### kotlin-ta - Kotlin Technical Analysis library
### Paulo Schlup
### https://github.com/pschlup/kotlin-ta

kotlin-ta is a technical analysis and back testing library for testing trading strategies and indicators which use chart data saved in CSV files for calculations and can handle multiple candle chart timeframes simultaneously. All the basic functions from an currency exchange are available which allows the user to focus on testing their strategies and indicators.

## Reflection
I have made multiple attempts previously to write a program in python for back testing and technical analysis, each with limited success before coming to a roadblock and deciding to start overusing a different approach or trying out a design pattern. This was slightly due to poor commit management, but more so because I already understand how trading exchanges work and all the functions they provide, so I know what to expect from my app when I’m building it. So, rebuilding allowed me to explore programming in a fun way. 
What bothered me is python isn’t likely to be a language that I’m going to be using professionally, at least not in the beginning of my web/mobile app development career, but I will use Kotlin. While I likely won’t be using much data science either, at least I have found a way to bring my little hobby into Kotlin which I really enjoy as a language. A big surprise for me was finding I could use kotlin in Jupyter notebooks which adore for their visual clarity layout. I guess what I’m trying to say is I am really excited to have found so many parallels to my interests in Kotlin that I look forward to seeing how this plays out.

# Independent Kotlin Overview Research - Part 2

The [Kotlin-ta](https://github.com/pschlup/kotlin-ta/) repo is separated into [4 directories](https://github.com/pschlup/kotlin-ta/tree/master/src/main/kotlin/com/pschlup/ta):

* [Backtest](https://github.com/pschlup/kotlin-ta/tree/master/src/main/kotlin/com/pschlup/ta/backtest)
* [Indicators](https://github.com/pschlup/kotlin-ta/tree/master/src/main/kotlin/com/pschlup/ta/indicators)
* [Strategy](https://github.com/pschlup/kotlin-ta/tree/master/src/main/kotlin/com/pschlup/ta/strategy)
* [Timeseries](https://github.com/pschlup/kotlin-ta/tree/master/src/main/kotlin/com/pschlup/ta/timeseries)

I'm going to examine the [indicators section](https://github.com/pschlup/kotlin-ta/tree/master/src/main/kotlin/com/pschlup/ta/indicators) due to my previous interests in this area. The indicator section of a trading application is generally referring to an algorithm that takes in bar or candlestick values ove the course of a period of time and finds patterns through analysis and calculation and displaying that data in a formatted way to the user.

For the purposes of this submission, I'll need to mention that the bar/candlestick sample data mentioned above is being stored in the [same repository in CSV files](https://github.com/pschlup/kotlin-ta/tree/master/sampledata) with an internal structure of:

“date”, “open”, “high”, “low”, “close”, “volume”

### Code Snippet #1 - Indicator.kt (Interface)
```
@file:Suppress("unused")

package com.pschlup.ta.indicators

/** Provides a single value at the specified time series bar index. */
fun interface Indicator {
  fun valueAt(index: Int): Double

  operator fun get(index: Int) = valueAt(index)
}

/** Convenience getter for the latest indicator value.  */
val Indicator.latestValue: Double get() = valueAt(0)

/** The value of the indicator delayed by the specified number of bars. */
fun Indicator.previousValue(bars: Int): Indicator = Indicator { index -> valueAt(index + bars) }
```
I didn't expect to find an interface here, I figured the data would be plugged directly into any indicator functions themselves. But given what I understand about interfaces it only makes sense to manage this data with one. Something I did not account for in my own "Market Simulator" as I called it using the bitfinex REST endpoints to pull the data, save to CSV, then unpack the CSV directly into my arrays which I feed to my indicators.

This interface in particular is detailing that our indicators must implement a <i>valueAt()</i> function which gets a value at the provided index number of the array holding the historical data for the indicators that use this interface.

<i>Indicator.latestValue()</i> Is a getter function which can access the Indicator and pull out the latest value which is going to be the 0 index in the array since with every timeseries update, a new bar will be created pushing  previous bar data further back in the array.

<i>Indicator.previousValue(bars: Int)</i> This was another suprise to me as I always manipulated my historical values in my data arrays directly by index, but I can clearly see how having a standard interface for different indicators is valuable and would have paid dividens in productivity through clarity. Having to remember the different ways i've implemented and pulled data from my past algorithms was difficult to manage at times and most likely only managable by me.

### Noteable Kotlin Coding Conventions / Idioms
1. [Source file names](https://kotlinlang.org/docs/coding-conventions.html#source-file-names) - If a Kotlin file contains a single class or interface (potentially with related top-level declarations), its name should be the same as the name of the class, with the .kt extension appended. It applies to all types of classes and interfaces.

2. [Naming Rules](https://kotlinlang.org/docs/coding-conventions.html#naming-rules) - Names of packages are always lowercase and do not use underscores (org.example.project). Using multi-word names is generally discouraged, but if you do need to use multiple words, you can either just concatenate them together or use camel case (org.example.myProject).


### Code Snippet #2 - Indicators.kt
```
@file:Suppress("unused", "DuplicatedCode")

package com.pschlup.ta.indicators

import com.pschlup.ta.timeseries.TimeSeries
import com.pschlup.ta.timeseries.UnstablePeriodException
import kotlin.math.abs
import kotlin.math.max

// ===========================================================
// Basic price indicators
// ===========================================================

val TimeSeries.openPrice: Indicator
  get() = Indicator { index -> this[index].open }

val TimeSeries.highPrice: Indicator
  get() = Indicator { index -> this[index].high }

val TimeSeries.lowPrice: Indicator
  get() = Indicator { index -> this[index].low }

val TimeSeries.closePrice: Indicator
  get() = Indicator { index -> this[index].close }

val TimeSeries.volume: Indicator
  get() = Indicator { index -> this[index].volume }

val TimeSeries.hlc3Price: Indicator
  get() = typicalPrice
```

So we're pulling in a Timeseries, so 30m, 1hr intervals and getting the open,high,low,close,vol,hlc3Price. So TimeSeries must handle reading the CSV files, and filter the data into the timeframe we want and we make indicators for each one of the values. Each indicator using the Indicator interface.

Again this is different than my approach, where that data was stored in a pandas dataframe for each. This way using the interface is much cleaner

### Noteable Kotlin Coding Conventions / Idioms
1. [Choose good names](https://kotlinlang.org/docs/coding-conventions.html#choose-good-names) - The name of a class is usually a noun or a noun phrase explaining what the class is: List, PersonReader. 
2. [Horizontal whitespace](https://kotlinlang.org/docs/coding-conventions.html#horizontal-whitespace) - Never put a space after (, [, or before ], ) Never put a space around . or ?.: foo.bar().filter { it > 2 }.joinToString(), foo?.bar(); Put a space after //: // This is a comment


### Code Snippet #3 - Indicators.kt (Function SMA)
```
/**
 * Calculates the Simple Moving Average (SMA) of another indicator.
 *
 * Usage:
 *    val h1Sma30 = h1.closePrice.sma(length = 30)
 */
fun Indicator.simpleMovingAverage(length: Int = 20) =
  Indicator { index ->
    (index until index + length).map { i -> this[i] }.average()
  }
```
This is a relatively simple indicator function that takes in a length of time (or number of bars/candlesticks) in the timeframe we specific (default of 20 bars -or- 20 hours on an hourly candle change) and maps the values in the Indicators array to get it's average. In this case the 20hr Simple Moving Average. But I thought it was a really good example of a basic simple indicator.

### Noteable Kotlin Coding Conventions / Idioms
1. [Default values for function parameters](https://kotlinlang.org/docs/idioms.html#default-values-for-function-parameters)
```
fun foo(a: Int = 0, b: String = "") { ... }
```

# Reflection
Looking at the various conventions and idioms was my biggest take away from the Kotlin Overview and it seems obvious that it's something I should be leaving open beside me when I code however I've spent a lot of time thinking about the structure of code that I've written in the past as I have a tendency of trying to do everything from scratch when I don't have to.

I had fun analyzing the Kotlin-ta repo and comparing it against my own "Market Simulator" which is a complete mess right now due to my lazy use of version control in a repo that started as a bit of a sandbox. But it brings to light a few important things I need to consider more and thats the tools I need to work faster and actually using those tools when appropriote like Coding conventions and idioms which I also mentioned was my biggest take away from this assignment. 

Now concerning me writing code from scratch when it wasn't necessary as I mentioned above in my summary, I don't think that was a waste of time but I do think it's time for me to break that habit and transition into a work flow that focuses on paying attention to more effective work flows polished by my predecessors. Though I admit I'm finding it difficult to break bad habits i've formed coding before pursing a formal education in this program.

I'm trying to find ways to reinforce my learning and make it more effective given there is so much to learn and I haven't gotten an efficient workflow down yet but more and more it seems to be one of my biggest flaws. I didn't go too much into detail around the conventions and idioms used in the Kotlin-ta repo but I did check more than I mentioned and I found that they put a positive effort into conforming to accepted conventions and idioms. I like the structure that it brings, and I can see it bringing confidence to the code and being able to justify it's use.
