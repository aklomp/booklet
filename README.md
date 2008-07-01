# Booklet: a script for making A5 booklets on A4 paper

Here's a little TeX script I wrote to scratch an itch of mine: how to
consolidate an A5 PDF document into an A4 PDF ready to throw through a duplex
printer and bind into a booklet? I've done it manually in my highschool days and
it's no fun. The first and last page have to be adjacent on one sheet, as do the
second page and the one before last. It quickly gets messy from there. So I
wrote this little script to automate it for me. It takes an A5 PDF file as input
and places the proper pages adjacently, until the PDF runs out. The result is an
A4 document ready for binding. Schematically:

![Graphic explanation of what the script does](booklet.png "Booklet graphic")

## Usage

Linux users: change the line with the filename into the one you'd like to page,
then run:

```sh
pdftex booklet.tex
```

This will produce a file called *booklet.pdf* in your current directory.

Windows users: change the line with the filename into the absolute path of your
PDF file, using forward slashes, such as `C:/alfred/input.pdf`. Then go to the
directory containing `pdfTeX` and run something like:

```sh
pdftex c:\alfred\booklet.tex
```

You'll find a file named *booklet.pdf* somewhere, either in the current
directory or in the directory where the script is located.

## A6 booklets, A4 booklets, A3 booklets, A2 booklets....

This script is by no means restricted to A5 booklets. All it does is take an
input file and embed its pages in the correct order into a new document. You'll
notice that the script doesn't assume any paper size for the input and doesn't
have to, because it just sticks the input pages in the top left and right
corners of the page respectively. In fact, the only sizes known to the script
are the height and width of the output, in this case A4 landscape. You're free
to redefine those sizes if you want to make different sized booklets, like A6
booklets on A5 paper (210mm wide, 148mm high), or A4 booklets on A3 paper (420mm
wide, 297mm high), or some other weird configuration.
