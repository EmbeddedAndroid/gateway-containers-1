# Copyright (c) 2019 Foundries.io
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
#

FROM alpine:latest

LABEL maintainer="Michael Scott <mike@foundries.io>"

RUN apk add --no-cache radvd dbus

COPY radvd.conf.template /etc/radvd.conf.template
COPY test.sh /test.sh
COPY interface-monitor.sh interface-monitor.sh
COPY start.sh start.sh

# Make a dbus dir for volume mount / symlink
RUN mkdir -p /var/dbus

ENTRYPOINT ["/start.sh"]
