https://gist.github.com/olivierpierre/21423ad8005ab6321aae8912c954cda2

Compress a directory tree into a tarball using pigz


#!/bin/sh

if [ "$1" == "" ]; then
	echo "Usage: $0 <folder to compress>"
	exit
fi

NAME=`basename $1`

tar -c --use-compress-program=pigz -f $NAME.tar.gz $NAME

  --------------------------------------------------------------
  
 Uncompress a directory tree contained in a tarball with pigz

  
  #!/bin/sh

if [ "$1" == "" ]; then
	echo "Usage: $0 <file to uncompress>"
	exit
fi

pigz -dc $1 | tar xf -
