# docker-osx

Docker on OS X in three steps:

1. Install [VirtualBox](https://www.virtualbox.org/wiki/Downloads).
1. Clone this repo and put the bin dir onto your PATH.
1. Run docker commands as normal!

See `bin/docker help` for help specific to this command.

## Example

Let's build a base image!

1. `docker build -t precise/base ./base-image`

Hey you should now have an image, neato!

Want to save that image locally for re-use later?

1. `docker save precise/base > precise-base.tar.gz`

## Hard Disk Persistence using Virtualbox

The default boot2docker disk is a bit small. We create a 40G space for you in VBox, but you need to take advantage of it with the following if you have a larger build:

```
sudo -s
fdisk /dev/sda
n      # new primary partition
p
1      # first partition
Enter  # default start
Enter  # default end
w      # write partition table and quit
mkfs.ext4 /dev/sda1
reboot
```

## Contributors

* [Will Farrington](https://github.com/wfarr) - all the new shiny stuff here!
* [Julien Duponchelle](https://github.com/noplay/) – Original author
* [Ben Firshman](https://github.com/bfirsh) – Faster and simpler installation with Vagrant image and pre-built binary

## Licence

### Some bits

Copyright 2014 Will Farrington

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.

### Some other bits

Copyright 2013 Julien Duponchelle

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
