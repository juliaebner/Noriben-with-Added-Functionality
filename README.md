# Noriben-with-Added-Functionality
The Noriben.py script from https://github.com/Rurik/Noriben has been extended to include the following functionality:
- The report now includes an "Analysis" section indicating whether any patterns of Trickbot malware were found. This is done using regular expressions each matching typical Trickbot operations. Patterns for other malware may be created in a similar manner.
- Any child processes that were created by malware are included in the report. This was done by using a bad_pid_list that is appended to with malicious process ID's and checked against the PID and parent PID in every event.
  - Note: To use the parent PID, you have to replace the "TID" column in ProcMon with the "Parent PID" column. This column layout can be saved as the default in Procmon by selecting File > Export configuration.
- The CreateFile and CreateFolder operations were replaced by WriteFile and WriteFolder to limit the report to changes made to files.
- The operations "TCP Reconnect" and "TCP Disconnect" were added to see more network traffic.

The whitelist was extended extensively to include every background process that was found on a Windows 10 Pro virtual machine running on Microsoft Azure. You will likely need to make adjustment or start off with the smaller whitelist from the original Noriben script. It is helpful to use a small app like the Windows Calculator to create the whitelist, where everything that has nothing to do with the Calculator will be a normal background process.

# Copyright [2019] [Julia Ebner]

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    https://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
