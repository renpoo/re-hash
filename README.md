# Re-Hash

Re-Hash is a tiny improvement of the well-known hash function -- djb2 --.

## Source Code (Core)

```

unsigned int re_hash( const char *word )
{
    unsigned long int hash = 1;

    int c;
    while ( (c = *word++) ) {
        hash += (hash << 7) + c; // Renpoo's improvement on djb2 (1)
    }

    return( hash & HASHSIZEMINUSONE );

}

```


## Author

* **Koji Sato (a.k.a. Renpoo Tsukioka)** - [GitHub](https://github.com/renpoo/)

## License

This project is licensed under the GPL3 or later - see the [GPL-LICENSE.md](GPL-LICENSE.md) file for details

## Acknowledgments

Great Thanks to Mr. Daniel J. Bernstein.

