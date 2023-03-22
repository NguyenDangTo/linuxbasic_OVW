### The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!)

- **mkdir /tmp/dangto** to create a dir name dangto

- **cp data.txt /tmp/dangto** to go copy data.txt to dangto dir

- **cd /tmp/dangto** to go to dangto dir

- **xxd -r data > data** to convert hexdump to binary

- **file data** to check type of file. we get type of file

##### Use **mv** to change name of data to type of zip then decompress it

1. **gzip -d data.gz** to decompress data.gz

2. **bzip2 -d data.bz2** to decompress data.bz2

3. **tar -xvf data.tar** to decompress data.gz

### Password: wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
