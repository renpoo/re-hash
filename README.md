# Re-Hash

Re-Hash is a tiny improvement of the well-known hash function -- djb2 --.

## Source Code (Core)

'''

unsigned int hash( const char *word )
{
    unsigned long int hash = 5381;

    int c;
    while ( (c = *word++) ) {
        hash += (hash << 7) + c; // Renpoo's improvement on djb2 (1)
    }

    return( hash & HASHSIZEMINUSONE );

}

'''


## Author

* **Koji Sato** - [GitHub](https://github/renpoo)

## License

This project is licensed under the GPL3 or later - see the [GPL-LICENSE.md](GPL-LICENSE.md) file for details

## Acknowledgments

Great Thanks to Mr. Daniel J. Bernstein.

