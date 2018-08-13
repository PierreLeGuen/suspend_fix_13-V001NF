# suspend_fix_13-V001NF
## The reason why you need a service
The Spectre 13 has a strange behavior with suspend under Linux. The power button blocks the suspend.
The /proc/acpi/wakeup file can be edited directly, but your modification won't stay. The service is here to disable it definitely.
## Installation

<pre><code>
git clone https://github.com/PierreLeGuen/suspend_fix_13-V001NF
cd suspend_fix_13-V001NF
sudo cp suspendfix_pwrb.service /etc/systemd/system
sudo systemctl enable suspendfix_pwrb.service
sudo shutdown -r now
</code></pre>

## How to check if it works

<pre><code>
sudo nano /proc/acpi/wakeup
</code></pre>

The line with PWRB should be "disabled"
