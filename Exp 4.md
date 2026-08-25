# Ex.No.4 – Email Header Analysis Using MHA

## Aim

To analyze email headers and detect possible email spoofing using **MHA (Mail Header Analyzer)**.

---

## Objective

- To understand the structure of email headers.
- To analyze the path followed by an email.
- To examine sender and receiver information.
- To verify SPF, DKIM, and DMARC authentication results.
- To identify suspicious IP addresses, hostnames, and domain mismatches.
- To detect possible email spoofing or phishing attempts.

---

## Introduction

An email header contains metadata about an email and provides information about its journey from the sender to the recipient.

Important header fields such as **From, To, Date, Subject, Return-Path, Received, Message-ID, SPF, and DKIM** can be analyzed to identify suspicious or spoofed emails.

The `Received` fields are particularly important because they show the servers through which the email passed. :contentReference[oaicite:1]{index=1}

---

## Tools Required

- MHA (Mail Header Analyzer)
- Gmail / Outlook / Yahoo Mail
- WHOIS or IP Lookup Service
- MXToolbox or Google G Suite Toolbox

---

## Procedure

### Step 1: Access the Email Header

#### Gmail

1. Open the email.
2. Click the three dots (**More**) in the upper-right corner.
3. Select **Show original**.

#### Outlook

1. Open the email.
2. Click **File**.
3. Select **Properties**.
4. Locate the **Internet headers** section.

#### Yahoo Mail

1. Open the email.
2. Click the three dots (**More**).
3. Select **View raw message**.

---

### Step 2: Copy the Email Header

Copy the complete email header.

The header contains metadata describing the email's journey from the sender to the recipient. :contentReference[oaicite:2]{index=2}

---

## Step 3: Identify Important Header Fields

| Header Field | Description |
|---|---|
| `From` | Email address of the sender |
| `To` | Email address of the recipient |
| `Date` | Date and time the email was sent |
| `Subject` | Subject of the email |
| `Return-Path` | Return address used if the email bounces |
| `Received` | Servers through which the email passed |
| `Message-ID` | Unique identifier of the email |
| `SPF` | Verifies whether the sender IP is authorized |
| `DKIM` | Helps verify email integrity |

---

## Step 4: Analyze the Received Fields

The `Received` fields show the path followed by the email from the sender to the recipient.

They are generally listed in reverse order, from the last server to the first server. :contentReference[oaicite:3]{index=3}

Each `Received` entry can contain:

- Sending server hostname/IP address
- Receiving server hostname/IP address
- Date and time of transmission

---

## Step 5: Check IP Addresses and Hostnames

Identify the IP addresses and hostnames present in the `Received` fields.

Use WHOIS or an IP lookup service to investigate:

- IP ownership
- Geographic information
- Hostname
- Whether the IP belongs to the expected mail server

Suspicious or unexpected IP addresses may indicate a possible spoofing attempt. :contentReference[oaicite:4]{index=4}

---

## Step 6: Examine SPF, DKIM and DMARC

### SPF – Sender Policy Framework

SPF checks whether the sender's IP address is authorized to send email for the domain.

<img width="1647" height="817" alt="1 (8)" src="https://github.com/user-attachments/assets/df5b3f74-a43e-46b1-8357-42ad43392f7b" />
<img width="1171" height="636" alt="2 (4)" src="https://github.com/user-attachments/assets/47871190-1aa9-438f-9931-0bc64e1e6966" />
<img width="742" height="237" alt="3 (7)" src="https://github.com/user-attachments/assets/3edb2604-da46-4f61-9c0e-5893cadbf543" />
<img width="1442" height="328" alt="4 (4)" src="https://github.com/user-attachments/assets/59a8c0e0-9253-4ac8-bf80-f5602d316343" />
<img width="1438" height="770" alt="5 (6)" src="https://github.com/user-attachments/assets/f812157e-b827-4748-a400-d1932d0d1b23" />
<img width="1657" height="695" alt="6 (5)" src="https://github.com/user-attachments/assets/c482c535-51eb-461a-9d0e-6d825c34155a" />
