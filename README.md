# google-hacking

The purpose of this repository is to aggregate all the google advanced query search operators that I could find. I was unable to locate complete, exhaustive, official documentation. Rather, I had to peruse multiple, unofficial sources. I have tried to combine these sources into a single table. The sources are located at the bottom under the "Google Hacking Sources" heading.

This repository is licensed under the [Creative Commons Zero v1.0 Universal License](https://choosealicense.com/licenses/cc0-1.0/) to allow the broadest use of the information. It is intended purely for the public domain.

## Google Hacking Operators
All google hacking operators are contained below and logically grouped by their function.

### Logical Search Operators
These search operators allow you to construct searches via basic logic. Including whole strings, partial strings, setting and/or/not logic of strings, setting string proximity, etc. The following operators are demonstrated in the context of conducting an OSINT investigation to understand funding for the American Heart Association.

| Operator | Description | Syntax | Example |
| :------: | :---------- | :----: | :-----: |
| * | Matches anything. | {string} * {string} | American Heart Association * Donors |
| "" | The string must match exactly (case-insensitive). | "{string}" | "American Heart Association" |
| AND | Match this term as well. This is technically implicit in any search with a space and is usually redundant. | {string} + {string} | American + Heart + Association (equivalent to searching: American Heart Association) |
| OR | Match the first term or the second term. | {string} OR {string} | American Heart Association OR AHA |
| \| | See "OR Operator" above. | {string} OR {string} | American Heart Association \| AHA |
| - | Exclude the term that follows the operator. | -{string} | AHA -donation |
| #..# | Search a range of numbers, including the ends. | {number}..{number} | AHA donations for 2000..2010 |
| AROUND(n) | Match pages containing the search terms separated by at most n words. | {string} AROUND(5) {string} | American Heart Association AROUND(5) funding |
| () | Group many terms and operators, allows construction of more advanced searches. | ({terms and operators}) | American Heart Association AND (funding OR donors OR fundraising) |

### Scope Restricting Search Operators
These operators narrow the broad scope of a search through different methods such as time, specific websites, url contents, etc.
| Operator | Description | Syntax | Example |
| :------: | :---------- | :----: | :-----: |
| site | Search only on a given site. The argument may also be a TLD such as com, net, etc. | site:{domain} | site:google.com |
| after | Search for results after a given date | {string} after:{yyyy-mm-dd} | covid after:2024-01-01 |
| before | Search for results before a given date | {string} before:{yyyy-mm-dd} | drop-shipping before:2015-06-03 |

### Topic-Specific Search Operators
These operators allow you to search for a specific type of information about something, like the weather, stock price information, information about movies, etc.
| Operator | Description | Syntax | Example |
| :------: | :---------- | :----: | :-----: |
| define: | Search for the definition of a word. | define:{string} | define:system |

| map: | Return only map results of a given topic. | map:{string} | map:Dallas |
| movie: | Search for information about a specific move. | movie:{string} | movie:Interstellar |
| source: | Search for results from a specific news source. | {search string} source:{source string} | election source:CBS |
| stocks: | Search for information about a specific stock. | stock:{string} | stocks:META |
| weather: | Search for information about the weather of the given location. | weather:{string} | weather:Dallas |

### Deprecated Search Operators
These search operators used to work but are now deprecated. Knowing what you can't do is as important as knowing what you cannot do.
| Operator | Description | Deprecated |
| :------: | :---------- | :--------: |
| + | Functioned the same as the AND operator. | 2011 |
| # | Search for hashtags in google+. | 2019 |
| ~ | Search for synonyms. | 2013 |
| allinpostauthor: | Search for posts by a specific author in the discontinued Google Blog Search, but without quotes. | N/A |
| info:, id: | Search for information about a specific page or website. | 2017 |
| inpostauthor: | Search for posts by a specific author in the discontinued Google Blog Search. | N/A |
| inposttitle: | Search for posts with certain words in the title in Google’s discontinued Blog Search. | N/A |
| link: | Search for pages linking to a particular domain or URL. | 2017 |
| phonebook: | Search for someone's phone number. | 2010 |

## Google Hacking Sources
- [Ahrefs Blog: Google Advanced Search Operators](https://ahrefs.com/blog/google-advanced-search-operators/)
- [StationX: Google Dorks Cheat Sheet](https://www.stationx.net/google-dorks-cheat-sheet/)
- [Recorded Future: Google Dorks](https://www.recordedfuture.com/threat-intelligence-101/threat-analysis-techniques/google-dorks)
- [Google Guide Cheat Sheet](https://www.googleguide.com/print/adv_op_ref.pdf)
- [NordVPN: What are Google dorks?](https://nordvpn.com/blog/google-hacks/)
- [ExploitDB: Google Hacking Database](https://www.exploit-db.com/google-hacking-database)
- [Splunk: Google Dorking](https://www.splunk.com/en_us/blog/learn/google-dorking.html)
