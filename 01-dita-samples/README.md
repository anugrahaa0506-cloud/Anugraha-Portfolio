# AirPods Connectivity Guide — DITA Sample Set

**Author:** Anugraha S  
**Type:** DITA XML Portfolio Sample  
**Tools used:** oXygen XML Editor, DITA 1.3 standard  

---

> **About this sample**
> This is a three-topic DITA documentation set written using publicly available Apple AirPods product information. It demonstrates the three core DITA topic types — concept, task, and reference — linked together via a DITA map. The `.dita` and `.ditamap` source files are available in this folder and can be opened in oXygen XML Editor.

---

## Topic 1 — Concept: Understanding AirPods Bluetooth Connectivity

**File:** `concept-airpods-bluetooth.dita`  
**Purpose:** Explains background knowledge. No steps, no commands — pure conceptual understanding.

---

### What this topic covers

AirPods use Bluetooth 5.0 technology to establish a wireless connection with Apple devices. Understanding how this connection works helps you troubleshoot issues and maintain a stable audio experience.

### How Bluetooth pairing works

Bluetooth is a short-range wireless communication standard that allows devices to exchange data over distances of up to 10 metres. When you pair AirPods with a device for the first time, the two devices exchange security keys and store each other's identities. This is called **pairing**. After pairing, the devices can reconnect automatically without repeating the full pairing process.

AirPods use Apple's **W1** or **H1** chip (depending on the model) to manage Bluetooth connections. These chips enable faster pairing, improved connection stability, and automatic switching between devices signed in to the same Apple ID.

### iCloud-based automatic pairing

When you pair AirPods with one Apple device signed in to your iCloud account, they are automatically available on all other Apple devices using the same Apple ID — including iPhone, iPad, Mac, and Apple Watch. You do not need to manually pair them to each device.

Automatic switching allows AirPods to detect which device you are actively using and transfer the audio connection without manual input.

### AirPods connection states

| State | Description |
|-------|-------------|
| Paired and connected | AirPods are actively connected and ready to play audio. |
| Paired but disconnected | AirPods are recognised by the device but not actively connected. They reconnect automatically when taken out of the case. |
| In pairing mode | AirPods are discoverable and ready to pair with a new device. Indicated by white flashing light. |
| Not charged | Insufficient battery to establish or maintain a Bluetooth connection. |

### Factors that affect Bluetooth connectivity

- Physical obstructions such as walls or furniture between AirPods and the device
- Wireless interference from other Bluetooth devices or Wi-Fi routers on the 2.4 GHz band
- Distance exceeding approximately 10 metres
- Outdated firmware on the AirPods or operating system on the connected device
- Too many paired devices stored in AirPods memory

---

## Topic 2 — Task: Reconnecting AirPods to an iPhone

**File:** `task-reconnect-airpods.dita`  
**Purpose:** Step-by-step procedure. Numbered steps, prerequisites, expected results.

---

### Before you begin

- Your AirPods have sufficient charge. Place them in the charging case for at least 15 minutes if the battery is low.
- Bluetooth is enabled on your iPhone. Go to **Settings** and confirm that **Bluetooth** is toggled on.
- Your iPhone is running iOS 14 or later.

### Steps

1. Place both AirPods in the charging case and close the lid. Wait 15 seconds before proceeding — this resets the AirPods' active connection state.

2. On your iPhone, open **Settings**.

3. Tap **Bluetooth**. The Bluetooth screen shows all previously paired devices. Your AirPods should appear under **My Devices**.

4. Open the AirPods charging case lid while holding the case close to your iPhone. The AirPods status should change from **Not Connected** to **Connected** within a few seconds.

5. If the AirPods do not connect automatically, tap the name of your AirPods in the Bluetooth list. Your iPhone initiates a manual connection request.

### Result

Your AirPods are now connected to your iPhone. Audio from your iPhone will route through the AirPods automatically. You will see the AirPods battery indicator in the iPhone status bar or in the Batteries widget.

### If this doesn't work

Proceed to a full reset: press and hold the setup button on the back of the AirPods case for 15 seconds until the LED flashes amber, then white. Re-pair from scratch.

---

## Topic 3 — Reference: AirPods LED Status Indicators

**File:** `reference-airpods-led-indicators.dita`  
**Purpose:** Lookup content. Tables, lists, specifications — content users return to repeatedly.

---

### LED location by model

- **AirPods (1st generation):** LED is inside the case lid, visible when open.
- **AirPods (2nd generation and later):** LED is on the front of the case, visible when closed.
- **AirPods Pro (all generations):** LED is on the front of the MagSafe charging case.

### LED status reference

| LED pattern | AirPods in case | AirPods not in case |
|-------------|-----------------|---------------------|
| Green (solid) | AirPods are fully charged. | Case is fully charged. |
| Amber (solid) | AirPods are charging. Less than one full charge remaining in case. | Case has less than one full charge remaining. |
| White (flashing) | AirPods are in pairing mode, ready to connect to a new device. | Not applicable. |
| Amber (flashing) | A pairing error has occurred. Reset before pairing again. | Not applicable. |
| No light | Case battery depleted, or AirPods fully charged with lid closed. | Case battery depleted. |

### Checking battery levels without the LED

- Open the AirPods case near your paired iPhone — a battery card appears showing charge levels for each AirPod and the case separately.
- Add the **Batteries** widget to your iPhone Home Screen.
- Ask Siri: "What is my AirPods battery level?"
- On Mac, click the Bluetooth icon in the menu bar and hover over your AirPods name.

---

## DITA Map Structure

**File:** `airpods-connectivity-guide.ditamap`

The ditamap organises all three topics in reading order:

```
airpods-connectivity-guide.ditamap
├── concept-airpods-bluetooth.dita       (background understanding)
├── task-reconnect-airpods.dita          (step-by-step procedure)
└── reference-airpods-led-indicators.dita (status reference table)
```

This order follows DITA best practice: concept first (understand the domain), task second (perform the action), reference last (look up specific details as needed).
