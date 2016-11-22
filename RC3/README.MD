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
