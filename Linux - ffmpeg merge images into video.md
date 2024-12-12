---
type: article
fc-calendar: Gregorian Calendar
fc-date: 
year: 2024
month: April
day: 08
creation date: 2024-04-08 12:36
modification date: Monday 8th April 2024 12:36:41
---

#internetContent  #scripting/ffmpeg 
## Article link:

related notes: 
- [[]]
_____
## Content

```
ffmpeg -r 30 -f image2 -s 540x540 -i "%07d.png" -vcodec libx264 -crf 17 -pix_fmt yuv420p output.mp4
```