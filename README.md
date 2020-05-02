# EOS Camera Movie Record

This software writes short movies with your digital DSLR camera Canon (R) directly to computer. The camera must have LiveView feature to work, like in Canon EOS 450D for example. The Program has preview, Av, Tv and WB control.

Source code:
https://sourceforge.net/projects/eos-movrec/


## Alternative

```
gphoto2 \
    --set-config viewfinder=1 \
    --set-config capturetarget='Memory card' \
    --set-config movierecordtarget=Card \
    --wait-event 10s \
    --set-config movierecordtarget=None \
    --wait-event-and-download 2s \
    --set-config viewfinder=0 \
```

The ordering and the exact spelling of the targets are important. Before starting to record (`movierecordtarget=Card`), the viewfinder needs to be enabled and capturetarget set to `Memory card` (not `Card`). You can use `--get-config capturetarget` and `--get-config movierecordtarget` to figure out the exact names of the targets, in case there are differences between camera models.

Source:
https://github.com/gphoto/libgphoto2/issues/135#issuecomment-522907763