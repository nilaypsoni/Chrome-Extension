# Chrome-Extension 🏆

## How is works. 🔧
Currently, this works by filtering through all the post, and
checking if each one of them is advertisement or not. If
it is advertisement, then it’s “style.display” property is
flex, else, it’s “style.display” property is none. This is
handled in hideIfSponsered() function. This function also
receives each post container as parameter. Once we find
that the container is of other posts rather than of the
advertisement, we hide them. Else, we show them.
After filtering whether it is advertisement or not, we
extract likes, comments, shares, page name, images,
profile icon, video (in blob url), and store it in data array,
which is sent to our database in every 30 seconds
interval. Once sent to our server, the data array is
cleared, and next advertisements are pushed in data
array.

## The current state of development 🔨
Currently, we can only extract information that the dom
has. The post link is also not available in the dom. So, we
are missing the link to the original post. The links to
pages are available in the dom, so we can extract it. Also, 
the video url is in blob format, and is of no use for us
now, even if we have extracted it.
I have tried sending entire HTML markup of the video
advertisement container and store it, and later inject it in
manually in dom, loaded by facebook, and copy the url of
the post ourself and store it in database. (If this would
work, we could set up bot for doing this, instead of doing
manually).
Also, I have tried to replace the video src attribute loaded
in our own facebook, with the blob url extracted, this
threw an error in facebook, and video couldn’t be
loaded.
