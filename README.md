# Jobsort

[Jobsort](https://jobsort.com) is a fast job search engine for developers. Jobsort is powered by a domain-specific language called JobSort Query Language (JSQL) which allows for deep job searching. The database of jobs is updated every few days.

Thanks to those who have given words of advice over the past months to guide future development. The name Jobsort comes from the well-known sorting algorithm Quicksort.

### JobSort Query Language (JSQL)

```
[-]keyword [[-]lang:string] [[-]tech:string] [[-]company:string] [[-]stage:string] [[-]hq:string] [remote:ok] [days:<uint] [size:<uint] [sort:datetime|traffic]
```

The `-` operator negates the meaning of the filter. For example, when searching for `java`, most search engines also return less relevant `javascript` hits. Thus, search for [`java -javascript`](https://jobsort.com/search?q=java+-javascript) to filter out `javascript` hits when looking for `java` jobs.

Filter | Syntax | Type | Examples
---|---|---|---
Keyword[^1] | `[-]keyword` | `string` | [`java`](https://jobsort.com/search?q=java), [`java -javascript`](https://jobsort.com/search?q=java+-javascript)
Programming Language[^3] | `[-]lang:` | `string`, see [languages.tsv](languages.tsv) | [`lang:go`](https://jobsort.com/search?q=lang:go), [`frontend -lang:php`](https://jobsort.com/search?q=frontend+-lang:php)
Tech Stack[^4] | `[-]tech:` | `string`, see [technologies.tsv](technologies.tsv) | [`tech:django`](https://jobsort.com/search?q=tech:django), [`sysadmin -tech:linux`](https://jobsort.com/search?q=sysadmin+-tech:linux)
Company | `[-]company:` | `string`, see [companies.csv](companies.csv) | [`company:apple`](https://jobsort.com/search?q=company:apple)
Stage | `[-]stage:` | `string`, see [stages.txt](stages.txt) | [`stage:seed`](https://jobsort.com/search?q=stage:seed'), [`stage:"series a"`](https://jobsort.com/search?q=stage:'series+a')
Headquarters | `[-]hq:` | `string` | [`hq:california -hq:"san francisco"`](https://jobsort.com/search?q=hq:california+-hq:'san+francisco')
Size | `size:<`, `size:>` | `uint` (employees) | [`size:<100`](https://jobsort.com/search?q=size:<100)
Remote[^2] | `remote:` | `ok` | [`remote:ok`](https://jobsort.com/search?q=remote:ok)
Recency[^5] | `days:<` | `uint` | [`days:<7`](https://jobsort.com/search?q=days:<7)
Sort Order[^6] | `sort:` | `rank\|datetime\|traffic\|random` | [`sort:datetime`](https://jobsort.com/search?q=sort:datetime), [`sort:random`](https://jobsort.com/search?q=sort:random), [`sort:traffic`](https://jobsort.com/search?q=sort:traffic)

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
