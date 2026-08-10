# Digital Forensics

## Ex. No. 1: Evidence Acquisition Using AccessData FTK Imager

### Date
10-08-2026

---

## Aim

To acquire volatile and non-volatile forensic evidence using **AccessData FTK Imager**.

---

## Description

**Forensic Toolkit (FTK)** is a computer forensics software product developed by AccessData. It is a Windows-based commercial product.

A free version of the commercial product, **FTK Imager**, is available with fewer functionalities. FTK Imager can be used for both acquiring and analyzing computer forensic evidence.

The evidence acquired using FTK Imager can be divided into two main categories:

- Acquiring volatile memory
- Acquiring non-volatile memory (Hard Disk)

---

## Methods of Evidence Acquisition

There are two possible ways FTK Imager can be used for forensic image acquisition:

### 1. Portable Version

FTK Imager can be stored on a USB pen drive or HDD and opened directly from the evidence machine.

This method is frequently used for **live data acquisition** when the evidence computer is switched on.

### 2. Installed Version

FTK Imager can be installed on the investigator's laptop.

In this case, the source disk should be connected to the investigator's laptop through a **write blocker**.

A write blocker:

- Prevents modification of data on the evidence source disk.
- Provides read-only access to the investigator's laptop.
- Helps maintain the integrity of the source disk.

---

# Acquiring Volatile Memory Using FTK Imager

FTK Imager can be used to collect the complete **volatile memory (RAM)** of a computer.

### Procedure

1. Open **FTK Imager**.
2. Navigate to the **Capture Memory** option.
3. Select the required destination folder.
4. Enable the required memory acquisition options.
5. Start the memory capture.

### Pagefile

The **pagefile (`pagefile.sys`)** is used by Windows as virtual memory when the physical RAM capacity is exceeded.

It is located under the `C` partition and can contain valuable information related to volatile memory.

Therefore, it is recommended to capture the pagefile during acquisition.

### AD1 File

**AD1** is an FTK Imager image file.

FTK Imager provides an option to create an AD1 file for later use.

After clicking **Capture Memory**, the volatile memory acquisition begins.

Once acquisition is completed, the destination folder contains the acquired memory file with the `.mem` extension.

---

# Acquiring Non-Volatile Memory (Disk Image)

FTK Imager can also be used to acquire a forensic disk image.

### Procedure

1. Open **FTK Imager**.
2. Select **Create Disk Image**.
3. Select the source that needs to be acquired.
4. Select the appropriate drive.
5. Configure the image destination.
6. Configure the image format and fragment size.
7. Enable image verification.
8. Start the acquisition.

FTK Imager can acquire:

- Physical drives
- Logical drives (partitions)
- Image files
- Folder contents
- CDs/DVDs

External HDDs can be connected to the collection computer through a **write blocker** and acquired using the logical drive option.

---

# Collecting Physical Drives

To collect a physical drive:

1. Select **Physical Drive**.
2. Select the drive that needs to be acquired.
3. Click **Finish**.

---

# Disk Image Formats

## 1. Raw (dd)

Raw (`dd`) is an image format commonly used by modern forensic analysis tools.

Raw images:

- Do not contain headers.
- Do not contain metadata.
- Do not contain magic values.
- Typically include padding for memory ranges that were intentionally skipped or could not be read.

The padding helps maintain spatial integrity and relative offsets among data.

---

## 2. SMART

SMART is a file format designed for Linux file systems.

It stores disk images as pure bitstreams with optional compression.

The file consists of a standard 13-byte header followed by sections containing information such as:

- Section type
- Offset to the next section
- Section size
- Padding
- CRC
- Actual data or comments

---

## 3. E01

**E01** is a proprietary forensic image format developed by Guidance Software's EnCase.

Characteristics include:

- Compression of the image file.
- Case information stored in the header and footer.
- MD5 hash of the entire bitstream.
- Date and time of acquisition.
- Examiner's name.
- Special notes.
- Optional password.

---

## 4. AFF

**AFF (Advanced Forensic Format)** was developed by Simson Garfinkel and Basis Technology.

Its latest implementation is **AFF4**.

The goal of AFF is to provide a disk image format that does not lock investigators into a proprietary format that could restrict analysis.

---

# Image Destination and Fragment Size

After selecting the image format:

1. Enter the case details.
2. Specify the image destination.
3. Enter the image file name.
4. Specify the fragment size.

### Image Fragment Size

The image fragment size determines whether the acquired image is divided into multiple files.

- Setting a fragment size creates multiple image files.
- Setting the fragment size to `0` creates a single image file.

---

# Image Verification

Select the:

**Verify images after they are created**

option.

This verifies the hash values after the image has been created.

Image verification is recommended because it helps ensure the integrity of the acquired evidence.

However, verification increases the time required for acquisition, especially for large disk images.

---

# Acquisition

Click **Start** to begin the evidence acquisition process.

After acquisition is completed, FTK Imager creates a text file containing information about the acquired evidence.

The hash values are then matched to verify the integrity of the evidence.

---

# Result

The volatile and non-volatile forensic evidence can be successfully acquired using **AccessData FTK Imager**.

The acquired evidence can be verified using hash values to help ensure its integrity.


<img width="347" height="247" alt="6" src="https://github.com/user-attachments/assets/2e8b20a0-f9d5-41be-92e0-9cb27a0aa93a" />

<img width="1460" height="1077" alt="5 (2)" src="https://github.com/user-attachments/assets/2aef1fa0-b3fb-4e52-b0bd-385b61f92958" />


<img width="171" height="121" alt="1 - Copy" src="https://github.com/user-attachments/assets/4ce0e84e-4606-4d65-8a33-cf9b21b08641" />


<img width="340" height="275" alt="2" src="https://github.com/user-attachments/assets/90d7da3b-7d30-4596-ad2c-1c660b53359a" />


<img width="340" height="272" alt="3" src="https://github.com/user-attachments/assets/a668a336-a03b-4644-b6a4-0d91b7ee3e86" />


<img width="343" height="246" alt="4" src="https://github.com/user-attachments/assets/aba790cc-f084-4949-9e37-06c78b667aad" />


<img width="959" height="272" alt="10" src="https://github.com/user-attachments/assets/ea40c0f9-cca0-4d0d-b9ba-24801845b998" />


<img width="1240" height="1269" alt="11 (2)" src="https://github.com/user-attachments/assets/4ac29544-d414-43ac-9f67-1554db7968a1" />


<img width="310" height="322" alt="12" src="https://github.com/user-attachments/assets/06d22aac-2659-464b-984a-98e3a7020347" />

---

# Conclusion

FTK Imager provides forensic investigators with a method to acquire volatile memory and non-volatile disk images.

The use of write blockers, appropriate image formats, image verification, and hash matching helps maintain the integrity of forensic evidence during acquisition.
