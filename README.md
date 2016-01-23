# xls2json
Simple Python tool for converting XLS workbook data into JSON, with associated C# POCO classes and load code.

Depends on xlrd, included: https://github.com/python-excel/xlrd

xls2json is designed to provide a lightweight process by which XLS data is converted into JSON format and loaded into C# code; basically, it's a convenient wrapper around xlrd that makes a few assumptions about how you intend to use the XLS data.

These assumptions include the following:

The XLS data incudes three descriptor fields occuping the first three rows of data in a worbook:

Row 1: Comment describing the intent of the data field

Row 2: Defines the underlying data type (string, int float, bool, or "key" - which is currently a fancy way of saying "string")

Row 3: Defines the name to be used for the underlying data type in the JSON/POCO.

Optionally, xls2json can generate a C# POCO that can be used to load the JSON data; as currently implemented, this assumes a base class of type Data, which is not directly provided.

<a href=https://github.com/ktagawa/xls2json-unity>xls2json-unity</a>, a related project, provides a Data implementation as well as a simple loading system built on top of the <a href=https://github.com/lbv/litjson>LitJson</a> library.
