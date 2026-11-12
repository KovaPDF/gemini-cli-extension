# KovaPDF extension for Gemini CLI

KovaPDF lets an assistant work on PDF files for the person it helps: compress, merge, split, reorder or rotate pages, convert to and from Word, Excel and pictures, read the text of a scan, redact details for good with a proof list, check digital signatures, and convert Bangla or Hindi text between Bijoy, Kruti Dev and Unicode. People connect their own KovaPDF account, and every job uses that account's usual limits. Files are deleted within an hour.

## Install

```
gemini extensions install https://github.com/kovapdf/gemini-cli-extension
```

Then run `/mcp auth kovapdf` in Gemini CLI. It opens the KovaPDF connect page, where you sign in and choose what to allow.

## Tools

| Tool | What it does | Without an account |
|---|---|---|
| `verify_pdf_signature` | Checks every digital signature in a PDF: who signed, when, whether the document changed after signing, and whether the certificate is trusted. Returns a report. The file is not changed. | yes |
| `compress_pdf` | Makes a PDF smaller. Choose a level, or a target size in KB. Returns a link to the smaller PDF; the original is not changed. | yes |
| `merge_pdfs` | Joins two or more PDFs into one, in the order given. Returns a link to the merged PDF. | yes |
| `split_pdf` | Splits a PDF: every page on its own (all), chosen pages into one PDF (range), every N pages (every), or into parts under a size (size). Returns a link to a PDF or a ZIP of PDFs. | no |
| `organize_pages` | Builds a new PDF from the pages listed, in that order. Each item is a page number, or { page, rotate } with rotate 90, 180 or 270. Pages left out are deleted. The original is not changed. | no |
| `convert_pdf` | Converts a PDF to Word (word), Excel (excel) or pictures (jpg, png); or a Word, Excel, PowerPoint or OpenDocument file, or pictures, to PDF (pdf). Returns a link to the result. | no |
| `ocr_pdf` | Reads the text in a scanned PDF or a picture with text recognition. Returns the text and a link to a .txt file. Up to 30 pages per call; use pages to choose. | no |
| `redact_pdf` | Permanently removes words or kinds of details (email, phone, card, date, url, iban, ssn) from a copy of the PDF, and lists every place something was removed as proof. The original is not changed. | no |
| `bijoy_to_unicode` | Converts Bangla text typed in Bijoy (SutonnyMJ and similar fonts) to Unicode Bangla. English words are kept as they are. Pass the text, or a .txt file. | yes |
| `unicode_to_bijoy` | Converts Unicode Bangla text to Bijoy, for SutonnyMJ and similar fonts. Pass the text, or a .txt file. | yes |
| `kruti_to_unicode` | Converts Hindi text typed in Kruti Dev to Unicode Hindi. English words are kept as they are. Pass the text, or a .txt file. | yes |
| `get_job_result` | Returns the state of a job started by another KovaPDF tool and, when it is done, its download links and report. | yes |
| `get_my_usage` | Returns how many free tasks the connected account has left right now, and when the next one comes back. Reads only; changes nothing. | yes |
| `create_signature_request_draft` | Prepares a request for people to sign a PDF, without sending anything. Each signer gets a signature box on the last page. Returns a draft_id and a summary: show the summary to the person and ask them to confirm before calling send_signature_request. | no |
| `send_signature_request` | Sends a prepared draft: each signer gets an email with a link to sign. Only call this after the person has seen the draft's summary and clearly said to send it. | no |
| `list_signature_requests` | Lists the person's signature requests, newest first, with their status. | no |
| `get_signature_request` | Shows one signature request: its status and who has signed. | no |

Docs: https://www.kovapdf.com/developers/docs/connect

## Licence

The code and configuration here are under the MIT License (see `LICENSE`). The KovaPDF name, logo, icons and images are not licensed (see `NOTICE`).

Work done through this package is done with KovaPDF (https://www.kovapdf.com).

Privacy: https://www.kovapdf.com/legal/privacy · Terms: https://www.kovapdf.com/legal/terms · Security: see `SECURITY.md`.
