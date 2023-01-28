# Jobsort

[Jobsort](https://jobsort.com) is a fast job search engine for developers. Jobsort is powered by a domain-specific language called JobSort Query Language (JSQL) which allows for deep job searching. The database of jobs is updated every few days.

Thanks to those who have given words of advice over the past months to guide future development. The name Jobsort comes from the well-known sorting algorithm Quicksort.

### JobSort Query Language (JSQL)

```
[-]STRING [[-]lang:STRING] [[-]tech:STRING] [[-]company:STRING] [[-]stage:STRING] [[-]hq:STRING] [remote:ok] [days:<UINT] [size:<UINT] [sort:datetime|random|rank|traffic]
```

The `-` operator negates the meaning of the filter. For example, when searching for `java`, most search engines also return less relevant `javascript` hits. Thus, search for [`java -javascript`](https://jobsort.com/search?q=java+-javascript) to filter out `javascript` hits when looking for `java` jobs.

Filter Syntax | Examples
---|---
`[-]STRING` | [`java`](https://jobsort.com/search?q=java), [`java -javascript`](https://jobsort.com/search?q=java+-javascript)
`[-]lang:STRING` for programming languages, see [languages.tsv](languages.tsv) | [`lang:go`](https://jobsort.com/search?q=lang:go), [`frontend -lang:php`](https://jobsort.com/search?q=frontend+-lang:php)
`[-]tech:STRING` for tech stacks, see [technologies.tsv](technologies.tsv) | [`tech:django`](https://jobsort.com/search?q=tech:django), [`sysadmin -tech:linux`](https://jobsort.com/search?q=sysadmin+-tech:linux)
`[-]company:STRING` for company names, see [companies.csv](companies.csv) | [`company:apple`](https://jobsort.com/search?q=company:apple)
`[-]stage:STRING` for startup stages, see [stages.txt](stages.txt) | [`stage:seed`](https://jobsort.com/search?q=stage:seed'), [`stage:"series a"`](https://jobsort.com/search?q=stage:'series+a')
`[-]hq:STRING` for headquarters | [`hq:california -hq:"san francisco"`](https://jobsort.com/search?q=hq:california+-hq:'san+francisco')
`size:<UINT`, `size:>UINT` for number of employees | [`size:<100`](https://jobsort.com/search?q=size:<100)
`remote:ok` for remote jobs | [`remote:ok`](https://jobsort.com/search?q=remote:ok)
`days:<UINT` for recency | [`days:<7`](https://jobsort.com/search?q=days:<7)
`sort:` for sorting, see `rank\|datetime\|traffic\|random` | [`sort:datetime`](https://jobsort.com/search?q=sort:datetime), [`sort:random`](https://jobsort.com/search?q=sort:random), [`sort:traffic`](https://jobsort.com/search?q=sort:traffic)

#### Example Searches

*   [`java -javascript`](https://jobsort.com/search?q=java+-javascript) for when `java` matches `javascript` results but you're not a frontend engineer, thus it's useful to remove `javascript` results.
*   [`hq:california -hq:"san francisco"`](https://jobsort.com/search?q=hq:california+-hq:'san+francisco') for when you want to find a job somewhere in `California` but living in `San Francisco` is just too expensive.
*   [`size:<100`](https://jobsort.com/search?q=size:<100) if you like working in small companies with less than 100 employees.
*   [`size:>1000`](https://jobsort.com/search?q=size:>1000) if you like working in large companies with more than 1000 employees.

[^1]: Search like on Google.
[^2]: Returns only remote jobs; `ok` is the only enum value for `remote:`.
[^3]: Useful when you search for programming languages that are common English words.
[^4]: Useful when you love Django on Windows, but dislike Linux.
[^5]: Returns only jobs found in the last two days.
[^6]: Sorts the results either by its crawl time in ascending order or its traffic in descending order.
