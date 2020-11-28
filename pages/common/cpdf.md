# cpdf

> CLI to manipulate existing PDF files in a variety of ways.
> More information: <https://www.coherentpdf.com/cpdfmanual/cpdfmanual.html>.

- Select pages 1, 2, 3 and 6 from a source document and write those to a destination document:

`cpdf {{path/to/source_document.pdf}} {{1-3,6}} -o {{path/to/destination_document.pdf}}`

- Merge two documents into a new one:

`cpdf -merge {{path/to/source_document_one.pdf}} {{path/to/source_document_two.pdf}} -o {{path/to/destination_document.pdf}}`

- Show the bookmarks of a document:

`cpdf -list-bookmarks {{path/to/document.pdf}}`

- Split a file into single-page files `page001.pdf`, `page002.pdf` etc:

`cpdf -split {{path/to/source_document.pdf}} -o {{path/to/page%%%.pdf}}`

- Split a document into ten-page chunks, writing them to `chunk001.pdf`, `chunk002.pdf`, etc:

`cpdf -split {{path/to/document.pdf}} -o {{path/to/chunk%%%.pdf}} -chunk {{10}}`

- Encrypt a document using 128bit encryption, providing `fred` as owner password and `joe` as user password:

`cpdf -encrypt {{128bit}} {{fred}} {{joe}} {{path/to/source_document.pdf}} -o {{path/to/encrypted_document.pdf}}`

- Decrypt a document using the owner password `fred`:

`cpdf -decrypt {{path/to/encrypted_document.pdf}} owner={{fred}} -o {{path/to/decrypted_document.pdf}}`

- Encrypt a file with 128 bit AES encryption with an owner password but blank user password:

`cpdf -encrypt AES {{"pass"}} {{""}} {{path/to/source_document.pdf}} -o {{path/to/encrypted_document.pdf}}`

- Show the annotations of a document:

`cpdf -list-annotations {{path/to/document.pdf}}`

- Create a new document from an existing one with additional metadata:

`cpdf -set-metadata {{path/to/metadata.xml}} {{path/to/source_document.pdf}} -o {{path/to/destination_document.pdf}}`

- Output some information about a file:

`cpdf -info {{path/to/document.pdf}}`

- Output information about each page:

`cpdf -page-info {{path/to/document.pdf}}`
 
- Scale pages to A4 paper:

`cpdf -scale-to-fit a4portrait {{path/to/source_document.pdf}} -o {{path/to/destination_document.pdf}}`

- Crop a file:

`cpdf -crop {{"20mm 20mm 300mm 300mm"}} {{path/to/source_document_two.pdf}} -o {{path/to/destination_document.pdf}}`

- Add page numbers:

`cpdf -add-text {{"Page %Page of %EndPage"}} {{-top 100pt}} {{-font "Times-Roman"}} {{-font-size 20}} {{path/to/source_document.pdf}} -o {{path/to/destination_document.pdf}}`

- Stamp one PDF file over each page of another:

`cpdf -stamp-on {{path/to/stamp.pdf}} {{path/to/source_document.pdf}} -o {{path/to/destination_document.pdf}}`

- Attach a file to page 5:

`cpdf -attach-file {{path/to/attachment.ext}} -to-page {{5}} {{path/to/source_document.pdf}} -o {{path/to/destination_document.pdf}}`

- Combine several commands together using AND: flip a file vertically and stamp text, then encrypt.

`cpdf {{path/to/source_document.pdf}} -vflip AND -add-text {{"Page %Page"}} AND -encrypt 128bit {{owner_password}} {{""}} -o {{path/to/destination_document.pdf}}`

- Compress a file without loss of information:

`cpdf -squeeze {{path/to/source_document.pdf}} -o {{path/to/destination_document.pdf}}`

- Compress a file with the standalone PDF squeezer:

`cpdfsqueeze {{path/to/source_document.pdf}} -o {{path/to/destination_document.pdf}}`
