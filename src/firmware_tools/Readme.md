# NoLongerEvil Firmware Analysis Files

NoLongerEvil contains this statement:

> "Open Source Commitment
> We are committed to transparency and the right-to-repair movement. The firmware
> images and backend API server code will be open sourced soon, allowing the
> community to audit, improve, and self-host their own infrastructure."

In the meantime, I am providing these files extracted from the NoLongerEvil's
firmware so that users can understand how the firmware is built and how it works.

---

## 🛠️ Modifying the Firmware

The **`./bin/nolongerevil`** script in this directory is used to make the necessary changes to the **original firmware** to redirect all the traffic originally exchanged with Google's servers to one IP pointing to **`nolongerevil.com`**.

### **How it Works**

* **Custom CA:** A custom **Certificate Authority (CA)** is provided so that **TLS exchanges** with nolongerevil's backend IP, using the original `nest.com`/`google.com` domains, are considered secured.
* **Hosts File Modification:** Original Nest and Google domains are declared in the **hosts file**, all pointing to the `nolongerevil`'s backend server.

### **DNS Note**

However, the **A DNS record** for `nolongerevil.com` is pointing toward **Cloudflare**, so if you resolve it against public DNS, you will be directed to the site through Cloudflare.

---

## 📂 Included Files

The `./etc` and `./bin` directories contain files that are used to create the **NoLongerEvil mod** from an image of the original firmware.

---

## ⚠️ Note on Firmware Binaries

I voluntarily **removed the firmware's binaries** from this fork. If you need them, please go to the original project:

* **Original Project:** https://github.com/codykociemba/NoLongerEvil-Thermostat

