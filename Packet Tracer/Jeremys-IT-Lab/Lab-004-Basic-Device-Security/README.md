# Lab 004 - Basic Device Security

**Course:** [Jeremy's IT Lab - Day 04](https://youtu.be/IYbtai7Nu2g)  
**Software:** Cisco Packet Tracer  
**Topic:** Cisco IOS CLI, passwords, and saving configurations

## About this lab

For Day 04, I started working directly in the Cisco IOS command-line interface instead of just looking at the network topology. The lab had me make a few basic changes to a router, set passwords for privileged access, and check what those changes looked like in the configuration.

I used the router console for the exercise and took screenshots as I went.

## What I worked on

I started by entering privileged EXEC mode with `enable` and moving into global configuration mode with `configure terminal`. I then changed the router's hostname to `R1`.

After that, I practiced setting an `enable password`, checking the running configuration with `show running-config`, turning on `service password-encryption`, and adding an `enable secret`. At the end, I saved the configuration with `write` and checked `show startup-config`.

Here are the main commands I used, with the example password values left out of this README:

```text
enable
configure terminal
hostname R1
enable password <lab-password>
end
show running-config
configure terminal
service password-encryption
enable secret <lab-secret>
end
show running-config
write
show startup-config
```

The screenshots show some shortened Cisco IOS commands too, such as `conf t`, `show run`, and `do sh run`.

## What I noticed

One small thing that happened was when I typed `en` while already in global configuration mode. The router returned an **ambiguous command** message. It was a useful reminder to pay attention to the prompt: `Router>`, `Router#`, and `Router(config)#` aren't interchangeable.

I also compared the configuration before and after enabling password encryption. At first, the `enable password` was visible as plain text. After using `service password-encryption`, it appeared as a Type 7 value. That hides it from casual viewing, but Type 7 is reversible and shouldn't be treated as strong password protection.

When I added `enable secret`, I could see a separate Type 5 hash in the configuration. The `enable secret` takes precedence over `enable password` for privileged EXEC access when both are configured. Type 5 is an older hash format; on newer IOS platforms, stronger supported secret types are preferred.

## Saving the configuration

Near the end of the lab, I ran `write` and got an `[OK]` confirmation. I then used `show startup-config` and could see the saved configuration displayed. That helped connect the difference between the active running configuration and the configuration stored for the next boot.

## Screenshots

I kept screenshots of the CLI at different points in the exercise. They cover the initial configuration, the password-encryption change, adding the enable secret, and checking the saved configuration.

The files will be added here once uploaded to GitHub:

- `cli-01-hostname-password.png`
- `cli-02-password-encryption.png`
- `cli-03-enable-secret.png`
- `cli-04-running-config.png`
- `cli-05-save-startup-config.png`

## What I'm taking away

This lab helped me get more comfortable switching between Cisco IOS modes and reading the CLI prompt before entering commands. I also got to see why `enable secret` is different from a basic `enable password`, and why saving a configuration matters after making changes.

This was a basic CLI and device-security exercise, not a full router-hardening setup. I haven't documented SSH, user accounts, access control, or connectivity tests because those weren't part of the work shown here.

## Lab files

- `Lab-004.pkt` - Packet Tracer project (upload pending)
- CLI screenshots listed above (upload pending)

## Credit

Based on [Jeremy's IT Lab - Day 04](https://youtu.be/IYbtai7Nu2g). These are my study notes and screenshots from following the lab.
