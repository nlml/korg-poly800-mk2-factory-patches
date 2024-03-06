# korg-poly800-mk2-factory-patches

Instructions to restore a KORG Poly800 MkII factory patches from midi sysex data.

After trying many apps in Windows to transfer the sysex data, the only working solution I ended up with was to use `amidi` in Linux.

1. Download the file in this repo `MK2-poly800-2.syx`.
2. Connect a MIDI interface to the PC and to the MIDI input of the Poly800 MkII.
3. Reboot the Poly800.
4. List midi devices with `amidi -l`, the output looks like this:
    ```
    amidi -l
    Dir Device    Name
    IO  hw:3,0,0  CH345 MIDI 1
    ```
5. Run `amidi -p hw:3,0,0 --sysex-interval=100 -s MK2-poly800-2.syx`
6. Reboot the synth again.
