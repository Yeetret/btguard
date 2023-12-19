
# BTGuard: A Simple Guide

## Overview

The `BTGuard` class is a powerful tool for enhancing the security of your software. It offers methods to:

1. Detect Debuggers
2. Detect If Current Machine is a Virtual Machine
3. Detect NPCAP (Sniffing Library)
4. Prevent Dumping
5. Anti Dll Injection
6. Anti Step-Over
7. Integrity Protection
8. Monitor Control
9. Program Detection
10. Anti Patching
11. Environment Checker
12. Bluescreen Control

## Quick Start: Code Example

Here's a quick example that demonstrates how to use the `BTGuard` class:

```cs
using System;
using System.Collections.Generic;
using System.Reflection;
using System.Threading.Tasks;

class Program
{
    static void Main(string[] args)
    {
        // Initialize BTGuard with license key
        BTGuard.BTGuard protection = new BTGuard.BTGuard("YourLicenseKeyHere");

        //Set to "true" if you want to send logs to your discord webhook
        protection.SendToWebhook(true);

        //If "SendToWebhook" is true then set your discord webhook and webhook username
        protection.SetDiscordWebhook("webhookHere", "usernameHere"); 
         
        //Enable Anti Debugging Protection
        protection.EnableAntiDebug();

        //Prevent Memory Dumping
        protection.PreventDumping();
        
        //Enable Anti Injection
        protection.EnableAntiInjection();
        
        //Enable Program Detection (Malicious or harmful applications that try to reverse or crack your application)
        protection.EnableProgramDetection();

        //Detect if current machine is Virtual Machine
        bool IsVM = protection.DetectVM();
        if(IsVM) { 
             //Your code here if current machine is a virtual machine.
        }
        
        //Detect if NPCAP is installed or running
        bool npcapInstalled = protection.IsNPCAPInstalled();
        if(npcapInstalled) { 
             //Your code here if npcap is detected.
        }

        //Methods to use with caution:
        
        //Turn off all monitors:
        protection.TurnOffMonitor();
       
        //Trigger Bluescreen:
        protection.TriggerBSOD();

        //Locks your mouse if true, if false then it unlocks your mouse and your keyboard (REQUIRES YOUR APPLICATION TO HAVE ADMINISTRATOR PERMISSIONS)
        protection.ToggleMouse(true);
    }
}
```
