# PDF parser (Demo)

POC - Data extraction from PDFs invoices
----

# Features:
- Parse pdfs invoices and extract data to XLSX/CSV 
- Sample pdfs with dummy data are included in [PDFS Sample](PDFs) folder

### Sample 1

Parse all pdfs files in /tmp/PDF, output to stdout, log level INFO  
```
$  pdf_extractor -p /tmp/PDF/ -LI
2021-12-16 10:35:34.954 INFO pdf_extractor - main: pdf_extractor v0.1.0 (2021-12-15) by ktxo
2021-12-16 10:35:34.955 INFO pdf_extractor - main: Python version 3.9.7 (default, Sep 16 2021, 13:09:58) [GCC 7.5.0]
2021-12-16 10:35:34.955 INFO pdf_extractor - main: PDFplumber version 0.5.28
2021-12-16 10:35:34.955 INFO pdf_extractor - main: Starting pid=70223
2021-12-16 10:35:34.955 INFO pdf_extractor - main: Using args Namespace(pdf_folder='/tmp/PDF/', silent=False, save=False, file_csv=None, file_xlsx=None, log=None, log_level='I', version=False)
2021-12-16 10:35:34.955 INFO pdf_extractor - main: Listing files from '/tmp/PDF/'
2021-12-16 10:35:34.955 INFO pdf_extractor - main: Found 5 files
     Filename                Invoice_Number    Invoice_Date    Customer         Item_Id  Item_Desription    Item_Quantity    Item_UnitPrice    Item_TotalPice
---  ----------------------  ----------------  --------------  -------------  ---------  -----------------  ---------------  ----------------  ----------------
  0  /tmp/PDF/factura01.pdf  Customer XX       2021-11-30      0001-00003990  109429223  Producto 005       229,33           100,00            22.933,00
  1  /tmp/PDF/factura01.pdf  Customer XX       2021-11-30      0001-00003990   13972918  Producto 004       170,00           100,00            17.000,00
  2  /tmp/PDF/factura01.pdf  Customer XX       2021-11-30      0001-00003990   20264787  Producto 006       46,67            50,50             2.356,84
  3  /tmp/PDF/factura01.pdf  Customer XX       2021-11-30      0001-00003990   23592498  Producto 010       76,33            1.100,00          83.963,00
  4  /tmp/PDF/factura01.pdf  Customer XX       2021-11-30      0001-00003990   37694557  Producto 002       263,33           12,01             3.162,59
  5  /tmp/PDF/factura01.pdf  Customer XX       2021-11-30      0001-00003990   50118803  Producto 009       9,67             1.100,00          10.637,00
  6  /tmp/PDF/factura01.pdf  Customer XX       2021-11-30      0001-00003990   64059291  Producto 003       68,00            120,20            8.173,60
...
108  /tmp/PDF/factura05.pdf  Customer AA       2021-12-01      0001-00004556   93134336  Producto 087       74,00            102,67            7.597,58
109  /tmp/PDF/factura05.pdf  Customer AA       2021-12-01      0001-00004556   95138136  Producto 101       86,00            236,33            20.324,38
    Filename                  Pages    Num_Items  Errors
--  ----------------------  -------  -----------  --------
 0  /tmp/PDF/factura01.pdf        1           10
 1  /tmp/PDF/factura02.pdf        1            1
 2  /tmp/PDF/factura03.pdf        1           12
 3  /tmp/PDF/factura04.pdf        2           35
 4  /tmp/PDF/factura05.pdf        2           52
2021-12-16 10:35:35.826 INFO pdf_extractor - main: Aplication end, pid=70223


```


### Sample 2
Sample 1, save output to excel file [invoices.xlsx](invoices.xlsx), don't print to stdout, log level INFO

```
$ pdf_extractor -p /tmp/PDF/ -S -s -fx invoices.xlsx -LI
2021-12-16 10:36:37.135 INFO pdf_extractor - main: pdf_extractor v0.1.0 (2021-12-15) by ktxo
2021-12-16 10:36:37.135 INFO pdf_extractor - main: Python version 3.9.7 (default, Sep 16 2021, 13:09:58) [GCC 7.5.0]
2021-12-16 10:36:37.135 INFO pdf_extractor - main: PDFplumber version 0.5.28
2021-12-16 10:36:37.135 INFO pdf_extractor - main: Starting pid=70338
2021-12-16 10:36:37.135 INFO pdf_extractor - main: Using args Namespace(pdf_folder='/tmp/PDF/', silent=True, save=True, file_csv=None, file_xlsx='invoices.xlsx', log=None, log_level='I', version=False)
2021-12-16 10:36:37.135 INFO pdf_extractor - main: Listing files from '/tmp/PDF/'
2021-12-16 10:36:37.135 INFO pdf_extractor - main: Found 5 files
2021-12-16 10:36:37.971 INFO pdf_extractor - save_output: Saving data to invoices.xlsx
    Filename                  Pages    Num_Items  Errors
--  ----------------------  -------  -----------  --------
 0  /tmp/PDF/factura01.pdf        1           10
 1  /tmp/PDF/factura02.pdf        1            1
 2  /tmp/PDF/factura03.pdf        1           12
 3  /tmp/PDF/factura04.pdf        2           35
 4  /tmp/PDF/factura05.pdf        2           52
2021-12-16 10:36:38.123 INFO pdf_extractor - main: Aplication end, pid=70338

```