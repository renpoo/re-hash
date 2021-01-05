# Re-Hash

Re-Hash is a tiny improvement of the well-known hash function -- djb2 --.

## Source Code

'''
/*
re-hash - re-hash.h
Copyright (c) 2021 Koji Sato (a.k.a. Renpoo Tsukioka)

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <https://www.gnu.org/licenses/>.
*/

#ifndef re_hash_h
#define re_hash_h


#ifndef HASHSIZE
#define HASHSIZE 65536
#define HASHSIZEMINUSONE (HASHSIZE - 1)
#endif


unsigned int hash( const char *word )
{
//    unsigned long int hash = 33;
    unsigned long int hash = 5381;

    int c;
    while ( (c = *word++) ) {
        hash += (hash << 7) + c; // Renpoo's improvement on djb2 (1)
//        hash += (hash << 8) + (c << 5) + c; // Renpoo's improvement on djb2 (2)
    }

    return( hash & HASHSIZEMINUSONE );

}

#endif /* re_hash_h */
'''


## Author

* **Koji Sato** - [GitHub](https://github/renpoo)

## License

This project is licensed under the GPL3 or later - see the [GPL-LICENSE.md](GPL-LICENSE.md) file for details

## Acknowledgments

Great Thanks to Mr. Daniel J. Bernstein.

