# IsadoraUserActors
A collection of useful Isadora User Actors

### DMX Light Actors

The DMX light actors are meant to be used in conjunction with a laptop running [QLC+](http://www.qlcplus.org/) listening to OSC together with a USB to DMX controller such as the [Enttec DMX USB PRO](https://www.enttec.com/eu/products/controls/dmx-usb/dmx-usb-pro/)

The `Midi Channel` input is the OSC channel the light has in QLC+ and is a remnant of the time we worked with QLC and MIDI. For example `Midi Channel` 10 means that the fixture in QLC+ will listen to a OSC message with the label `/10` and a value between 0.0 - 1.0.

#### Control Fresnel+.iua

This actor is used to control the [Elation Fresnel Led](http://www.elationlighting.com/eled-fresnel-ii) or any other single channel DMX fixture.

#### Control MovingHead+.iua

This actor is used to control a moving head met 8 DMX channels.

#### Control RGB Zoom lmap+.iua

This actor is used to control a [Design LED Par Zoom](http://www.elationlighting.com/design-led-par-zoom) or any other RGB zoom par with 5 DMX channels

#### Control RGBA+.iua

This actor is used to control a RGBA par or any other RGBA par with 4 DMX channels

### Korg Nano Controller

Use this actor to use a [Korg Nano Controller](http://www.korg.com/us/products/computergear/nanokontrol2/) with Isadora. Connect the Nano controller and go to: `Communications -> Midi Setup` to assig a input port to the nano controller. Make sure that the `MIDI Interface Port -main` is set to the same port as in the Midi Setup

### Limit-ScaleV2 (auto limits)

This user actor is based on a Limit-Scale actor with the ability to "learn" the actor what the minimal and maximum values are for the incoming values. Connect the incoming data (for instance a sensor) to the `Live-value` input and set `Learn` input to `on` and toggle the `reset` input.
The actor will now "learn" what the minimal and maximum values are that it receives and wil map these to the range you set with `out min` and `out max`. The `Min Hold` and `Max Hold` outputs show the range of the `Live-value` input.

### MovingHead_OSC_ECT_ion.iua

This user actor is used to connect with a [ECT ION](http://www.etcconnect.com/Products/Consoles/Eos-Family/Ion/Features.aspx) over OSC to control [Briteq Movingheads](https://briteq-lighting.com/bt-w19l10-zoom) with Isadora.

### Multi OSC listenr.iua

This user actor can be used to recieve a OSC message with multiple (9) values and will output each value to it's own user actor output.
The actor is geared towards use with the [NATNET2OSC bridge](https://github.com/hku-ect/NatNet2OSCbridge) to split an incoming rigidbody or skeleton joint message.

### QuarternionToEuler.iua

This user actor is made to use together with the [NATNET2OSC bridge](https://github.com/hku-ect/NatNet2OSCbridge) to convert the quarternion rotation of an object to euler angles. But can offcourse convert any Quarternion in Euler angles.

### Recieve Rigidbody.iua

This user actor is a comibnation of the Multi OSC listenr.iua and the QuarternionToEuler.iua. It will recieve an OSC message from the [NATNET2OSC bridge](https://github.com/hku-ect/NatNet2OSCbridge) and already converts the incoming Quarternion to Euler angles.
