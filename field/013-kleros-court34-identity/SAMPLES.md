# Run 013 — Court 34 Samples

10 evenly spaced disputes from court 34 (IDs 151..295).

| id  | category                  | title                                      |
|-----|---------------------------|--------------------------------------------|
| 151 | Image Generation          | Wrong Artistic Style in AI-Generated Painting |
| 166 | Agentic Commerce          | ¿Es válido el reclamo?                     |
| 181 | Oracle                    | Yoon out as president of South Korea       |
| 196 | Services                  | ¿Es válido el reclamo?                     |
| 211 | Services                  | ¿Es válido el reclamo?                     |
| 228 | Services                  | ¿Es válido el reclamo?                     |
| 243 | Services                  | Barnes v. Felix                            |
| 258 | Services                  | ¿Debería la empresa pagar la compensación? |
| 275 | Services                  | ¿Debería la empresa pagar la compensación? |
| 295 | prediction_market.mentions| Trump / Corn rally prediction              |

Method: for each id, find its tx in the block it was
created, fetch the tx receipt, decode the
DisputeTemplateRegistry event, parse the JSON.
