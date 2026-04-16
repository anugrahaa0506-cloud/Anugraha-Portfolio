# Wi-Fi Network Not Showing Up on Windows 11 — Troubleshooting Guide

**Product:** Windows 11 PC / Laptop  
**Component:** Wi-Fi adapter and network discovery  
**Last reviewed:** April 2026  

---

## Symptom

Your Wi-Fi network does not appear in the list of available networks on your Windows 11 device. Other networks may be visible, but your specific network is missing. Alternatively, no networks appear at all.

---

## Possible causes

| Cause | Likelihood |
|-------|-----------|
| Wi-Fi adapter is disabled | High |
| Router is broadcasting on 5 GHz only, device supports 2.4 GHz only | High |
| Network SSID (name) is hidden | Medium |
| Wi-Fi adapter driver is outdated or corrupted | Medium |
| Router requires a restart | Medium |
| Physical Wi-Fi switch on laptop is turned off | Low |

---

## Resolution steps

Work through these steps in order. Stop when the issue is resolved.

### Step 1 — Confirm Wi-Fi is enabled on your device

1. Click the **Network icon** in the taskbar (bottom-right corner).
2. Confirm the **Wi-Fi** tile is highlighted (active). If it appears greyed out, click it to enable Wi-Fi.
3. Check for a physical Wi-Fi switch or **Fn + F key** combination on your laptop that may have disabled the wireless adapter.

### Step 2 — Check if the router is functioning

1. Confirm the router's power light is on and stable (not flashing in an error pattern).
2. Check that at least one other device — a phone or another computer — can see and connect to the network. If no devices can find the network, the issue is with the router, not your PC.
3. Restart the router: unplug it from the power source, wait 30 seconds, then plug it back in. Allow 2 minutes for it to fully restart before checking your PC again.

### Step 3 — Check the frequency band

Modern routers broadcast on both **2.4 GHz** and **5 GHz** bands. Older laptops may only support 2.4 GHz.

1. Log in to your router's admin panel (typically at `192.168.1.1` or `192.168.0.1` in a browser).
2. Confirm both 2.4 GHz and 5 GHz bands are active.
3. If you have separate network names (SSIDs) for each band, make sure the 2.4 GHz network is enabled and broadcasting.

### Step 4 — Check if the network SSID is hidden

If your router is configured to hide its network name, it will not appear in the automatic network list. You can still connect manually.

1. Click the **Network icon** in the taskbar.
2. Click **Manage Wi-Fi connections**.
3. Scroll to the bottom and select **Hidden network**.
4. Enter the network name (SSID) and password exactly as configured on your router.

### Step 5 — Run the Windows network troubleshooter

1. Open **Settings** (Windows key + I).
2. Go to **System → Troubleshoot → Other troubleshooters**.
3. Click **Run** next to **Internet Connections**.
4. Follow the on-screen instructions. Windows will detect and attempt to fix common adapter and connectivity issues automatically.

### Step 6 — Update or reinstall the Wi-Fi adapter driver

1. Right-click the **Start button** and select **Device Manager**.
2. Expand **Network adapters**.
3. Right-click your Wi-Fi adapter and select **Update driver**.
4. Choose **Search automatically for drivers** and follow the prompts.
5. If no update is found, visit your laptop manufacturer's support website and download the latest Wi-Fi driver for your model manually.

### Step 7 — Reset network settings

> **Warning:** This step removes all saved Wi-Fi passwords and network configurations. You will need to re-enter credentials for all networks after completing this step.

1. Open **Settings → Network and Internet → Advanced network settings**.
2. Scroll to the bottom and click **Network reset**.
3. Click **Reset now** and confirm.
4. Your PC will restart. After restarting, reconnect to your Wi-Fi network using your password.

---

## Expected result

After completing the applicable step, your Wi-Fi network appears in the list of available networks. You can select it, enter the password, and establish a stable connection.

---

## If the issue persists

If your network is still not visible after all steps above:

- Test a different device on the same network to rule out a router configuration issue
- Check whether your ISP is experiencing an outage in your area
- Consider that the Wi-Fi adapter hardware may be faulty — contact your device manufacturer for diagnostic support
- For corporate or enterprise networks, contact your IT administrator, as the network may have MAC address filtering or other restrictions in place

---

*This article is a technical writing portfolio sample by Anugraha S, written using publicly available Microsoft and networking documentation as reference.*
