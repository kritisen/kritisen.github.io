---
layout: post
title: Filename Handling in MFC
published: true
---

## Filename Handling in MFC

Recently I was doing programming on MFC (Visual C++) and faced the need to do the following:

User would select a file from a file dialog box, and I got a CString for the full file path:  

`CString m_strIn= "C:\\Documents and Settings\\admin\\Desktop\\in.ext";`

I needed to generate a new string which had the suffix "_Filt" to use as output file name.

i.e. I needed

`CString m_strOut = "C:\\Documents and Settings\\admin\\Desktop\\in_Filt.ext"`

to be automatically generated.

I looked around for a while and found that MFC provides a lot of functions for getting file extensions from a string, for getting folder path from string etc. So I combined these and found that the following bit of code worked absolutely fine to generate my required string.

`char * file = _strdup(m_strIn);  

PathRemoveExtension(file);  

CString ext = PathFindExtension(m_ImgFileNameValue);  

m_strOut.Format("%s_Filt%s", file, ext);`
