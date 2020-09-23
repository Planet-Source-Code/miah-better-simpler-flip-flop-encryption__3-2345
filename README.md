<div align="center">

## Better, Simpler,  Flip\-Flop "encryption"


</div>

### Description

It reads the binary of a file, and outputs it in reverse so the new "encrypted" file can't be normally read. To decrypt encode the new file and it will be reversed again, restoring it back to normal. Its pretty handy, and simple, please rate this code.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Miah\!](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/miah.md)
**Level**          |Intermediate
**User Rating**    |3.5 (21 globes from 6 users)
**Compatibility**  |C\+\+ \(general\), Microsoft Visual C\+\+
**Category**       |[Security](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/security__3-14.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/miah-better-simpler-flip-flop-encryption__3-2345/archive/master.zip)

### API Declarations

```
#include <stdio.h>
```


### Source Code

```
/*
Backwerdz version 1.00 by Miah.
It takes a file, reads it from back to front,
and outputs it to a new backwards file that
can't be read normally.
Simple enough...
On with the code!
*/
#include <stdio.h>
main()
{
	char fileIn[30], fileOut[30];
	char byteBuff[1];
	int x=-1, Fsize;
	printf("\t\t\tMiah's Backwerdz file encoder\n");
	printf("\n\nEnter Filename to Encode/Decode: ");
		scanf("%s",fileIn);
	printf("\nEnter name to output file as: ");
		scanf("%s",fileOut);
FILE *in, *out;
	in = fopen(fileIn, "rb");     //Need that "b" so it can read binary too!
	out = fopen(fileOut, "wb");     //And write it..
fseek(in, 0, SEEK_END);
Fsize = ftell(in);      //This fTells us the size of the file by going to the end
               // and reading what the number of the last byte is
fseek(in, -1, SEEK_END);       //We seek a negative one (-1) from our position at the
									 //end of the file so we read it backwards
do
{
fseek(in, x, SEEK_END);
	fread(&byteBuff,1,1,in);     //read and write at the same time
	fwrite(&byteBuff,1,1,out);
x--;                 //Continue to countdown
Fsize--;               //Decrease size count so we can
}while(Fsize > 0);         //Break the loop when it reaches zero
fclose(in);           //Close It!
fclose(out);
return 0;
}
```

