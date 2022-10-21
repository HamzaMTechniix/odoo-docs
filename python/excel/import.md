# Import

```python
import base64, xlrd

class MtxExemple(models.Model)
    _name = 'mtx.exemple'
    
    xls_file = fields.Binary(string="Fichier Excel")
    
    def import(self):
        wb = xlrd.open_workbook(file_contents=base64.decodestring(self.xls_file))
        for sheet in wb.sheets():
             for row in range(sheet.nrows):
                 for col in range(sheet.ncols):
                     print(sheet.cell(row,col).value)
```
