# Victor DVT4

"Victor DVT4" prototypes are the last of the Design Validation Test batches for Vector.

The hardware here is final.

There are a couple software differences though:

* No unlock OTA have been found for a DVT4.
* Some may be prod-locked, but most have been found with Whiskey-like ABOOTs that are dev but don't have the anki.dev flag so they are locked to a specific kernel.
* No CPU fuses are set, so you could run a DVT2 aboot that allows you to run any kernel you want.

The body board in these are NOT normal and can only accept DVT3< firmware. They will not work for normal haeds. SWD is also locked, so upgrade isn't possible unless the chip is replaced.

These have serial numbers following this format: 00e1####

Some of these bots may boot up to an exclaimation point. Turning them upside-down then double (or triple) pressing the button will let them finish bootup. Then, you can shake them around to make them explore around.

![Anki Victor DVT4 Orange Boot](VicDVT4OB.jpg)

![Anki Victor DVT4](VicDVT4.jpg)