# pdfScraping
Meetup looking at scraping information from PDFs

---

Useful data is so often stored in pdfs, which are format designed primarily for printing but not so great for searching or indexing. The links to these pdfs are often presented in unhelpful lists on archive or categorised pages, which makes grabbing the information needed often tedious. 

Using with R or python packages we will attempt to design scraping tools to grab desired information, using the World Health Organisation's country profiles as an example:

<http://www.who.int/globalchange/resources/country-profiles/en/>

Hopefully the tools and skills that we cover will be useful outside of this example, and if anyone has similar examples then please comment them. Also this should be achievable in the time frame and then we can all go for a drink or food afterwards if people are keen. :)

---

Topics: 

* Manipulating css to grab key elements from a webpage

* Extracting desired text elements from online pdfs

* Data Munging

Bring: 

* Laptops, Charging Cords, an Inquisitive Spirit

Pre-Requisites: 

* Familiar with R - I will have a vague solution already done so I am more than happy to float around the room and help out with anyone using R (sadly I (OJ) can't help with python).

* Familiar with python 

---

## Rough Outline of Possible Solution 

* 1. Create a function that creats a vector of all the desired URLs on the malaria country profiles' page. 
  + Hint 1: This function should be able to use a css selector (".a_z a") to find the links, and then search for hyperlink atrributes ("href") to find the links.
  + Hint 2: For R users, the R package [rvest] and [xml2] will be very useful here.
* 2. Create a script to use the urls to download the corresponding PDFs and search for a text string whch preceeds the information of interest. 
  + Hint 1. After converting the pdf into text (R and Python [pdftools] and PDFMiner packages respectively) suitable string to search for would perhaps be "Reported confrmed cases:".
  + Hint 2: After findind the location ofthe string of interest, usig the following x number of characters the number of interest can be isolated using white space as word breaks. For R users, the string/character handling package [stringr] will be of help here. 
