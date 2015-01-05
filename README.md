# Matrox Monarch HD Controller

`monarchcontroller` is a python library to manage Matrox MonarchHD Devices.

The available commands reflect the Matrox API Documentation from the _Dev Tools Reference Guide_ December 9th 2014.
http://www.matrox.com/video/media/pdf/support/monarch_hd/doc/en_Matrox_Monarch_Dev_Tools_Reference_Guide_2_1_1.pdf
 
## Usage

```
from monarchcontroller import monarchhd
ctr = monarchhd('10.105.0.129', 'admin', 'password')
ctr.getStatus()
```

### Available Commands

#### GetStatus
This command is used to acquire the current stream and record status of a Monarch HD device.

#### StartStreaming
This command is used to start the stream function on a Monarch HD device that is set to RTMP mode.

#### StartRecording
This command is used to start the record function on a Monarch HD device.

#### StartStreamingAndRecording
This command is used to start the stream (RTMP mode) and record functions simultaneously on a Monarch HD device.

#### StopStreaming
This command is used to stop the stream function on a Monarch HD device that is set to RTMP mode.

#### StopRecording
This command is used to stop the record function on a Monarch HD device.

#### StopStreamingAndRecording
This command is used to stop the stream (RTMP mode) and record functions simultaneously on a Monarch HD device.

#### GetStreamingVideoDataRate
This command is used to acquire the average video data rate in kb/s (bit rate) that is currently 
programmed on the device. The device must be in Stream-only mode for this call to succeed.

#### SetStreamingVideoDataRate
This command is used to set the data rate (in kb/s) dynamically without stopping a current streaming operation. 
For this command to work, the device must be in Stream-only mode. The minimum data rate will be set to 90% of 
the average, and the maximum data rate will be set to 110% of the average.

#### SetRTSP
This command is used to set the RTSP URL and port, as well as switch the streaming mode to RTSP on the device. 
This command will always fail unless the device is idle (not streaming or recording).

#### GetRTSP
This command is used to get the URL and port that is currently programmed for RTSP streaming. 
Returning this call does not necessarily mean that the device is set to stream in RTSP mode.

#### SetRTMP
This command is used to configure the RTMP parameters and set the streaming mode to RTMP. 
This command will always fail unless the device is idle (not streaming or recording).

#### GetRTMP
This command is used to get the RMTP settings that are currently programmed. 
Returning this call does not necessarily mean that the device is set to stream in RTMP mode.


## Contributors

* Mathieu Habegger [@mhabegger](https://github.com/mhabegger)

## License

monarchcontroller
Copyright (C) 2015  SMP Solutions GmbH

This program is free software; you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation; either version 2 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License along
with this program; if not, write to the Free Software Foundation, Inc.,
51 Franklin Street, Fifth Floor, Boston, MA 02110-1301 USA.