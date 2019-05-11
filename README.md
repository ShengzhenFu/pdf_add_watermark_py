# pdf_add_watermark_py
please pip install PyPDF2 before you run script

This converter by default only support latin-1, if your encoding is not latin-1, so you need to change format to utf-8 like below

do remember to modify PyPDF2/utils.py in line 238 :
r = s.encode('latin-1')
replace it with the code below
try:
                r = s.encode('latin-1')
                if len(s) < 2:
                    bc[s] = r
                return r
            except Exception as e:
                print(s)
                r = s.encode('utf-8')
                if len(s) < 2:
                    bc[s] = r
                return r
