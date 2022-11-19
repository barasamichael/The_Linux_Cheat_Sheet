## wget linux command

wget is a non-interactive command line program for file downloading. It is useful for 
downloading content from web and FTP sites. It has options that allow reecursive 
download, background download and complete download of partially downloaded files.

It can also follow links in HTML, CSS and XML pages, to create local versions of 
remote web sites, fully recreating redirectory structure of original site i.e., 
recursive downloading

It however respects the Robot Exclusion Standard (/robots.txt)

### Examples

#### To download a single file

```sh
$ wget https://www.python.org

```

#### To download multiple  files, create a txt file and write the urls

```sh
$ cat links.txt
https://www.python.org
https://www.linkedin.com
https://www.geeksforgeeks.com

$ wget -i links.txt

```

#### To save downloaded file in a different name

```sh
$ wget -O custom_name.html https://www.python.org

```

#### To save files to a particular directory

```sh
$ wget -P documents/archives/ https://www.python.org

```

#### To limit download speed

```sh
$ wget --limit-rate=500k https://www.python.org

```

#### To set retry attempts

```sh
$ wget --tries=100 https://www.geeksforgeeks.com

```

#### To download in the background
```sh
$ wget -b https://www.python.org

```
`-a wget-log` file will appear in the working directory, which can be used to check
dwonload progress. To check the download progress and status enter:

```sh
$ tail -f wget-log

```

#### To download via ftp

```sh
$ wget --ftp-user=YOUR_USERNAME --ftp-password=YOUR_PASSWORD ftp://example.com/something.zip

```

#### To continue unterrupted downloads

```sh
$ wget -c https://www.python.org

```

The new file will have .1 added at the end as it already exists

#### To retrieve all websites

```sh
$ wget --mirror --convert-links --page-requisites --no-parent -P documents/websites/ https://www.python.org

```

##### Analysis

Option | Description
------ | -----------
--mirror | Directs wget to download recursively
--convert-links | Directs wget to convert all links for proper offline usage
--page-requisites | Directs wget to include all necessary files such as CSS, JS and images
--no-parent | Directs wget not to retrieve directories above hierarchy
-P documents/websites| Ensures that all the content goes to our specified directory

#### To locate broken links

```sh
$ wget -o wget-log -r -l 5 --spider https://www.python.org

```

##### Analysis

Option | Description
------ | -----------
-o wget-log | Gathers output into a file (wget-log) for later use
-l | Specifies recursion level (5 in our case)
-r | Makes download recursive
--spider | Sets wget to spider mode

To view the broken links, use the following command:

```sh
$ grep -B 2 '404' wget-log | grep "http" | cut -d "" -f 4 | sort -u

```

#### To download numbered files

```sh
$ wget https://www.example.com/images/{1..50}.jpg

```

#### To retrieve all .jpg images

```sh
$ wget -r -A .jpg https://site/with-images/url

```

### Authors
Kamau Ngengi - <ourdigitaltimes@gmail.com>

### Sources
[www.hostinger.com/tutorials/wget-command-examples/] (https://www.hostinger.com/tutorials/wget-command-examples/)
