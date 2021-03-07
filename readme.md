## deinit .env initialization

An opinionated interactive helper for initializing `.env` files for local checkouts. The concept is simple: the bash
script requires a `.env.required` file to use as a template. It looks for lines with `UNINITIALIZED=` variables, and
reads the _previous_ comment line for prompt text and additional instructions.

- Content after a pipe `|` character on the comment line is not printed
- Adding `@secret` to the end of the comment instruction line will inhibit output
- For a working example please see [examples](./examples/.env.required)

----

#### Example Output

    $ deinit
    ==> [INFO] setting up .env file
    ==> supports ; and # comment prefixes
    PHILIP_FRY=friday
    DOES_NOT_HAVE_DOC="specify value with or without quotes"
    ==> the secret directive is valid for multiple subsequent variables
    JOHN_ZOIDBERG=
    KIF_KROKER=
    ==> the important thing is that we don't panic
    HERMES_CONRAD=my_manwich
    ==> [DONE] completed .env saved

----

#### Installation

    curl -LsS https://raw.githubusercontent.com/typecoercion/dotenv-interactive/v0.0.1/deinit > /usr/local/bin/deinit
    chmod +x /usr/local/bin/deinit

#### Run Once

    bash <(curl -LsS https://raw.githubusercontent.com/typecoercion/dotenv-interactive/v0.0.1/deinit)
