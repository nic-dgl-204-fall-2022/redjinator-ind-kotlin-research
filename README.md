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

