## Logmein REV-100

This was an easy chall to solve using the angr framework & some static analysis.


```

import angr

def main():

    proj = angr.Project("logmein", load_options={"auto_load_libs": False})
	//find-> printing the flag, avoid -> printing wrongFlag
    pathgroup = proj.surveyors.Explorer(find=(0x4007F0, ), avoid=(0x4007C0,))

    pathgroup.run()
    return pathgroup.found[0].state.posix.dumps(0)

if __name__ == '__main__':
    print main()
    
```

`Flag is : RC3-2016-XORISGUD`

## Who's a good boy Web-100


Easy webchall..  looking at the sourcecode we see alot of jpg files and a css file beeing loaded.

``` <link rel="stylesheet" href="doge.css"/> ```

Opening the doge.css file we see the flag in cleartext.

`flag:RC3-2016-CanineSS `
