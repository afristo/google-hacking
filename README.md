# google-hacking

The purpose of this repository is to aggregate all the google advanced query search operators for conducting OSINT via google hacking. I was unable to locate complete, exhaustive, official documentation. Rather, I had to peruse multiple, unofficial sources. I have tried to combine these sources into a single table. The original sources are located at the bottom under the "Google Hacking Sources" heading.

If you have questions, comments, concerns or corrections, reach out to me via email: [me@andrefristo.com](mailto:me@andrefristo.com)

This repository is licensed under the [Creative Commons Zero v1.0 Universal License](https://choosealicense.com/licenses/cc0-1.0/) to allow the broadest use of the information. It is intended purely for the public domain.

## Google Hacking Operators
All google hacking operators are contained below and logically grouped by their function.

### Logical Search Operators
These search operators allow you to construct searches via basic logic. Including whole strings, partial strings, setting and/or/not logic, setting string proximity, etc. The following operators are demonstrated in the context of conducting an OSINT investigation into funding for the American Heart Association.

| Operator | Description | Syntax | Example |
| :------: | :---------- | :----: | :-----: |
| * | Matches anything. | {string} * {string} | American Heart Association * Donors |
| "" | The string must match exactly (case-insensitive). | "{string}" | "American Heart Association" |
| AND | Match this term as well. This is technically implicit in any search with a space and is usually redundant. | {string} + {string} | American + Heart + Association (equivalent to searching: American Heart Association) |
| OR | Match the first term or the second term. | {string} OR {string} | American Heart Association OR AHA |
| \| | Match the first term or the second term. | {string} OR {string} | American Heart Association \| AHA |
| - | Exclude the term that follows the operator. | -{string} | AHA -historical |
| #..# | Search a range of numbers, including the ends. | {number}..{number} | AHA donations for 2000..2010 |
| AROUND(n) | Match pages containing the search terms separated by at most n words. | {string} AROUND(5) {string} | American Heart Association AROUND(5) funding |
| () | Group many terms and operators, allows construction of more advanced searches. | ({terms and operators}) | American Heart Association AND (funding OR donors OR fundraising) |

### Scope Restricting Search Operators
These operators narrow the broad scope of a search through different methods such as time, specific websites, url contents, etc. The following operators are demonstrated in the context of conducting an OSINT investigation into funding for the American Heart Association.

| Operator | Description | Syntax | Example |
| :------: | :---------- | :----: | :-----: |
| @ | Restrict search to popular social media sites. Not as precise as the site: operator. | @{platform} {search string} | @youtube american heart association |
| after: | Search for results after a given date. | {string} after:{yyyy-mm-dd} | AHA donations after:2024-01-01 |
| allintitle: | Find results with multiple words in the title tag. | {search string} allintitle:{string} {string} | AHA allintitle:FY financial |
| allinurl: | Find results with multiple words in the url. | {search string} allinurl:{string} | AHA allinurl:files finance |
| allintext: | Find results with a multiple words in the text of the document. | {search string} allintext:{string} {string} | AHA allintext:donor contributions |
| before: | Search for results before a given date. | {string} before:{yyyy-mm-dd} | AHA biggest donors before:2015-06-03 |
| ext: | Search for results containing a [specific file extension](https://developers.google.com/search/docs/crawling-indexing/indexable-file-types) (identical to filetype: operator) (e.g. PDF, XLSX, etc.). | {search string} ext:{string} | AHA ext:pdf |
| filetype: | Search for results containing a [specific filetype](https://developers.google.com/search/docs/crawling-indexing/indexable-file-types) (identical to ext: operator) (e.g. PDF, XLSX, etc.). | {search string} filetype:{string} | AHA filetype:pdf |
| intext: | Find results with a specific word in the text of the document. | {search string} intext:{string} | AHA intext:donors |
| intitle: | Find results with a specific word in the title tag. | {search string} intitle:{string} | american heart association intitile:disclosure |
| inurl: | Find results with a specific word in the URL of the document. | {search string} inurl:{string} | american heart association inurl:finance |
| related: | Search for documents that are related to the given website. | {search string} related:{string} | donations related:heart.org |
| site: | Search only on a given site. The argument may also be a TLD such as com, net, etc. | {search string} site:{string} | donation site:heart.org |

### Topic-Specific Search Operators
These operators allow you to search for a specific type of information about something, like the weather, stock price information, information about movies, etc.

| Operator | Description | Syntax | Example |
| :------: | :---------- | :----: | :-----: |
| define: | Search for the definition of a word. | define:{string} | define:system |
| location: | Search for location specific information about a given topic. | location:{string} | location:dallas |
| map: | Return only map results of a given topic. | map:{string} | map:Dallas |
| movie: | Search for information about a specific move. | movie:{string} | movie:Interstellar |
| source: | Search for results from a specific news source. | {search string} source:{source string} | election source:CBS |
| stocks: | Search for information about a specific stock. | stocks:{string} | stocks:META |
| weather: | Search for information about the weather of the given location. | weather:{string} | weather:Dallas |

### Mathematical Search Operators
These operators allow you to use google as a calculator and other similar functions.

| Operator | Description | Example | Result |
| :------: | :---------- | :----: | :-----: |
| + | Addition | 2+2 | 4 |
| - | Subtraction | 1-3 | -2 |
| * | Multiplication | 2*3 | 6 |
| / | Division | 4/2 | 2 |
| % of | Percentage | 33% of 9 | 2.97 |
| X^Y, X**Y | Raise X to the power of Y.Both operators ^ and ** perform the same operation. | 3^2, 3**2 | 9 |
| in, to | Convert a quantity from a given unit to another. Translate words into another language. | 6 ft 2 inches in cm, 140 lbs in kg, 100 USD to bitcoin, 8 am London time to California time, thank you in spanish. | 6 ft 2 inches in cm = 187.96 |
| sqrt | Square root function. | sqrt(4) | 2 |
| i | Imaginary number. | i^2 | -1 |
| N choose R | Find how many combinations are possible from N items taken R at a time, where N and R are integers (combinatorics). | 6 choose 4 | 15 |
| sin, cos, tan | Trigonometric functions. You may specify the formula using symbols and natural language. | sin(pi/6), sin 30 degrees | sin(pi/6) = 0.5 |
| timer | A basic timer. | timer for 20 minutes | A visible, working timer. |
| N/A| Generate a random number. | flip a coin, roll a dice, show random number from 10 to 40 | tails |
| [graph] EXPRESSION [from A to B] | Graph a mathematical EXPRESSION with variables x and y on an (optional) numerical range from A to B. The “graph” keyword is only necessary if Google doesn’t understand your query. | sin(x)/x, graph log(x), sqrt(x^2+y^2) from -20 to 20 | A visibile, mathematical, plot. |

### Deprecated Search Operators
These search operators used to work but are now deprecated.
| Operator | Description | Deprecated |
| :------: | :---------- | :--------: |
| + | Functioned the same as the AND operator. | 2011 |
| # | Search for hashtags in google+. | 2019 |
| ~ | Search for synonyms. | 2013 |
| allinpostauthor: | Search for posts by a specific author in the discontinued Google Blog Search, but without quotes. | Unknown |
| cache: | Search for the cached version of a website. Uses Google's cache. URL must be *exact*. | 2024 |
| inanchor: | Find results using a specific anchor text. | Unknown |
| info:, id: | Search for information about a specific page or website. | 2017 |
| inpostauthor: | Search for posts by a specific author in the discontinued Google Blog Search. | Unknown |
| inposttitle: | Search for posts with certain words in the title in Google’s discontinued Blog Search. | Unknown |
| link:, links: | Search for pages linking to a particular domain or URL. | 2017 |
| phonebook: | Search for someone's phone number. | 2010 |

## Google Hacking Sources
- [Ahrefs Blog: Google Advanced Search Operators](https://ahrefs.com/blog/google-advanced-search-operators/)
- [StationX: Google Dorks Cheat Sheet](https://www.stationx.net/google-dorks-cheat-sheet/)
- [Recorded Future: Google Dorks](https://www.recordedfuture.com/threat-intelligence-101/threat-analysis-techniques/google-dorks)
- [Google Guide Cheat Sheet](https://www.googleguide.com/print/adv_op_ref.pdf)
- [NordVPN: What are Google dorks?](https://nordvpn.com/blog/google-hacks/)
- [ExploitDB: Google Hacking Database](https://www.exploit-db.com/google-hacking-database)
- [Splunk: Google Dorking](https://www.splunk.com/en_us/blog/learn/google-dorking.html)

Note - All queries were last tested in January, 2025.
