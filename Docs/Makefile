# Tell 'make' not to look for files with the following names
.PHONY : all

# By default, just build the docs
all :
	doxygen
	doxygen2docstring.py xml/index.xml GWFrames_Doc.i
	perl -p -i -e 's/(%feature\("docstring"\) .*)((?:<(?:[^<>]++|(?1))*>))/$$1 . join("",split(" ",$$2))/ge; s/%feature\("docstring"\).* (\S+) """/%feature\("docstring"\) $$1 """/' GWFrames_Doc.i
	perl -p -i -e 's/GWFrames::GWFrames::/GWFrames::/g' GWFrames_Doc.i
