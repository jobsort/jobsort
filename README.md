# Jobsort

[Jobsort](https://jobsort.com) is a fast job search engine for developers. Jobsort is powered by a domain-specific language called JobSort Query Language (JSQL) which allows for deep job searching. The database of jobs is updated every few days.

Thanks to those who have given words of advice over the past months to guide future development. The name Jobsort comes from the well-known sorting algorithm Quicksort.

> If you find Jobsort helpful, please consider staring the repo. It helps!

## JobSort Query Language (JSQL)

```
[-]STRING [-]lang:STRING [-]tech:STRING [-]visa:STRING [-]company:STRING [-]stage:STRING [-]hq:STRING date:<UINT size:>UINT remote:ok sort:datetime|random|rank|traffic
```

The `-` operator negates the meaning of the filter. For example, when searching for `java`, most search engines also return less relevant `javascript` hits. Thus, search for [`java -javascript`](https://jobsort.com/search?q=java+-javascript) to filter out `javascript` hits when looking for `java` jobs.

Filter Syntax | Filter Examples
---|---
`KEYWORD`, `-KEYWORD` | [`java`](https://jobsort.com/search?q=java), [`java -javascript`](https://jobsort.com/search?q=java+-javascript)
`lang:`, `-lang:` for programming languages; see [languages.tsv](languages.tsv) | [`lang:go`](https://jobsort.com/search?q=lang:go), [`frontend -lang:php`](https://jobsort.com/search?q=frontend+-lang:php)
`tech:`, `-tech:` for tech stacks; see [technologies.tsv](technologies.tsv) | [`tech:django`](https://jobsort.com/search?q=tech:django), [`sysadmin -tech:linux`](https://jobsort.com/search?q=sysadmin+-tech:linux)
`visa:`, `-visa:` for visa sponsorship; see [visas.tsv](visas.tsv) | [`visa:h1b`](https://jobsort.com/search?q=visa:h1b) (US full-time employee)
`company:`, `-company:` for company names; see [companies.csv](companies.csv) | [`company:apple`](https://jobsort.com/search?q=company:apple), [`company:'epic games'`](https://jobsort.com/search?q=company:'epic+games')
`stage:`, `-stage:` for startup stages; see [stages.txt](stages.txt) | [`stage:seed`](https://jobsort.com/search?q=stage:seed'), [`stage:'series a'`](https://jobsort.com/search?q=stage:'series+a'), [`stage:'series b'`](https://jobsort.com/search?q=stage:'series+b'), [`stage:'series c'`](https://jobsort.com/search?q=stage:'series+c'), [`-stage:public`](https://jobsort.com/search?q=-stage:public)
`hq:`, `-hq:` for company headquarters; see [companies.csv](companies.csv) | [`hq:california -hq:'san francisco'`](https://jobsort.com/search?q=hq:california+-hq:'san+francisco')
`size:<`, `size:>` for number of employees | [`size:<100`](https://jobsort.com/search?q=size:<100), [`size:>100`](https://jobsort.com/search?q=size:>100), [`size:>100 size:<1000`](https://jobsort.com/search?q=size:>100+size:<1000)
`date:<`, `date:>` for job published date; must be in days | [`date:<7`](https://jobsort.com/search?q=date:<7) (last week), [`date:<30`](https://jobsort.com/search?q=date:<30) (last month)
`remote:` for remote jobs; must be `ok` | [`remote:ok`](https://jobsort.com/search?q=remote:ok)
`sort:` for sorting; must be `datetime`, `random`, `rank`, `traffic` | [`sort:datetime`](https://jobsort.com/search?q=sort:datetime), [`sort:random`](https://jobsort.com/search?q=sort:random), [`sort:traffic`](https://jobsort.com/search?q=sort:traffic), [`sort:rank`](https://jobsort.com/search?q=sort:rank) (default)

Note that if a filter value contains whitespace, the value must be wrapped between `'` or `"`; either works, but examples herein use single quotes rather than double quotes.

> Please send an email to <info@jobsort.com> to request more filters.

## Example Searches

*   [`java -javascript`](https://jobsort.com/search?q=java+-javascript) for when `java` matches `javascript` results but you're not a frontend engineer, thus it's useful to remove `javascript` results.
*   [`hq:california -hq:"san francisco"`](https://jobsort.com/search?q=hq:california+-hq:'san+francisco') for when you want to find a job somewhere in `California` but living in `San Francisco` is just too expensive.
*   [`size:<100`](https://jobsort.com/search?q=size:<100) if you like working in small companies with less than 100 employees.
*   [`size:>1000`](https://jobsort.com/search?q=size:>1000) if you like working in large companies with more than 1000 employees.

## Visa Sponsorship

### United States Immigration

*   H-1B visa is for full-time employees (FTE); see [H-1B visa on Wikipedia](https://en.wikipedia.org/wiki/H-1B_visa)
*   E-3 visa is similar to H-1B but only for Australian citizens; see [E-3 visa on Wikipedia](https://en.wikipedia.org/wiki/E-3_visa)
*   TN visa is similar to H-1B but only for Canadian citizens or nationals of Mexico; see [TN status on Wikipedia](https://en.wikipedia.org/wiki/TN_status)
*   H-3 visa is for internships; see [H-3 visa on Wikipedia](https://en.wikipedia.org/wiki/H-3_visa)
*   F-1 visa is for full-time students; see [F-1 visa on Wikipedia](https://en.wikipedia.org/wiki/F_visa)
*   J-1 visa is for researchers, professors, and exchange visitors; see [J-1 visa on Wikipedia](https://en.wikipedia.org/wiki/J-1_visa)
