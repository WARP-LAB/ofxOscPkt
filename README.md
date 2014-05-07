ofxOscPkt
=========

Alternative to ofxOsc, Julien Pommiers OscPkt.

Using Julien Pommiers OscPkt in oF.

http://gruntthepeon.free.fr/oscpkt/

ofxOsc and Cinder OSC relies on oscpack lib. When sending OSC messages to node-osc from Cinder, everything works, but those sent from oF go are lost somewhere. Not saying that node-osc isn't to blame. Anyways, insted of trying to find and solve the issue, Julien lib with two headers is great alternative.

See Juliens original examples.

```
// To send a simple msg
oscpkt::UdpSocket oscPingSock; // instance variable
string oscPingIp = "127.0.0.1";
int oscPingPort = "8000";
oscPingSock.connectTo(oscPingIp, oscPingPort);
if (!oscPingSock.isOk()) {
  cerr << "Error connection to port " << oscPingPort << ": " << oscPingSock.errorMessage() << "\n";
}
oscpkt::Message msg("/ping");
msg.pushInt32(1);
oscpkt::PacketWriter pw;
pw.addMessage(msg);
oscPingSock.sendPacket(pw.packetData(), pw.packetSize());

```


```
/* Copyright (C) 2010  Julien Pommier

  This software is provided 'as-is', without any express or implied
  warranty.  In no event will the authors be held liable for any damages
  arising from the use of this software.

  Permission is granted to anyone to use this software for any purpose,
  including commercial applications, and to alter it and redistribute it
  freely, subject to the following restrictions:

  1. The origin of this software must not be misrepresented; you must not
     claim that you wrote the original software. If you use this software
     in a product, an acknowledgment in the product documentation would be
     appreciated but is not required.
  2. Altered source versions must be plainly marked as such, and must not be
     misrepresented as being the original software.
  3. This notice may not be removed or altered from any source distribution.

  (this is the zlib license)
*/
```
