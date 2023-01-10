Hi,

This is a repo containing Daniel R. Jordan's Maple Manual for Ken Rosen's __Discrete Mathematics and its Applications__.

The originals can be found [here](https://highered.mheducation.com/sites/125967651x/student_view0/exploring_discrete_mathematics_using_maple.html).

None of this is my own work, I just wanted to be able to wget the list of procedures in `rosen.txt` from a foreign machine.

I have extracted the procedures from the worksheet files with the following command:
```sh
❯ find . -iname "*chapter*" | cut -c3- | sort | xargs -I {}  echo 'Worksheet[WorksheetToMapleText]("./{}");' | maple > out.txt
```

I then cleaned up this file with **Vim** macros, leaving only the precious procedures.

Now, as I can find no way to import these procedures into the Maple commandline I have opted to leverage some unix pipe wizardry to access these procedures with:
```sh
(cat proc.txt; cat;) | maple
```
