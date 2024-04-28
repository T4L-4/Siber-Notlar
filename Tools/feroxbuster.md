Basic Usage:

    feroxbuster -u <url>

Specify wordlist:

    feroxbuster -u <url> -w <wordlist>

Choose the number of threads:

    feroxbuster -u <url> -t <number_of_threads>

Specify the user agent:

    feroxbuster -u <url> -H "User-Agent: <user_agent>"

Use cookies:

    feroxbuster -u <url> -C <cookie>

Follow redirects:

    feroxbuster -u <url> -r

Custom status code filter:

    feroxbuster -u <url> --filter-status <status_code>

Verbose output:

    feroxbuster -u <url> -v

Use SSL verification:

    feroxbuster -u <url> --insecure

Set a timeout:

    feroxbuster -u <url> --timeout <timeout_in_seconds>