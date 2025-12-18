# GDPR Compliance Checklist – Web-based Booking System

| **Result** | **Personal data mapping and minimization** |
| :----: | :--- |
| &nbsp;⚠️&nbsp;<br><sup><a id="note1-origin">[note 1](#note1)</a></sup> | Have all personal data collected and processed in the system been<br> identified? (e.g., name, email, age, username) |
| &nbsp;✅&nbsp; | Have you ensured that only necessary personal data is collected (data minimization)? |
| &nbsp;✅&nbsp; | Is user age recorded to verify that the booker is over 15 years old? |

---

| **Result** | **User registration and management** |
| :----: | :--- |
| &nbsp;✅&nbsp; | Does the registration form (page) include GDPR-compliant consent for processing<br> personal data (e.g., acceptance of the privacy policy)?|
| &nbsp;⚠️&nbsp;<br><sup><a id="note2-origin">[note 2](#note2)</a></sup> | Can users view, edit, and delete their own personal data via their account? |
| &nbsp;❌&nbsp; | Is there a mechanism for the administrator to delete a reserver in<br> accordance with the "right to be forgotten"? |
| &nbsp;✅&nbsp; | Is underage registration (under 15 years) and booking functionality restricted? |

---

| **Result** | **Booking visibility** |
| :----: | :--- |
| &nbsp;✅&nbsp; | Are bookings visible to non-logged-in users only at the resource level<br> (without any personal data)? |
| &nbsp;✅&nbsp; | Is it ensured that names, emails, or other personal data of bookers are not exposed<br> publicly or to unauthorized users? |

--- 

| **Result** | **Access control and authorization** |
| :----: | :--- |
| &nbsp;⚠️&nbsp;<br><sup><a id="note3-origin">[note 3](#note3)</a></sup> | Have you ensured that only administrators can add, modify, and delete<br> resources and bookings? |
| &nbsp;✅&nbsp; | Is the system using role-based access control (e.g., reserver vs. administrator)? |
| &nbsp;✅&nbsp; | Are administrator privileges limited to ensure GDPR compliance (e.g., administrators<br> cannot use data for unauthorized purposes)? |

---

| **Result** | **Privacy by Design Principles** |
| :----: | :--- |
| &nbsp;✅&nbsp; | Has Privacy by Default been implemented (e.g., collecting the minimum data by default)? |
| &nbsp;✅&nbsp; | Are logs implemented without unnecessarily storing personal data? |
| &nbsp;⚠️&nbsp;<br><sup><a id="note4-origin">[note 4](#note4)</a></sup> | Are forms and system components designed with data protection in mind<br> (e.g., secured login, minimal fields)? |

---

| **Result** | **Data security** |
| :----: | :--- |
| &nbsp;⚠️&nbsp;<br><sup><a id="note5-origin">[note 5](#note5)</a></sup> | Are CSRF, XSS, and SQL injection protections implemented? |
| &nbsp;✅&nbsp; | Are passwords securely hashed using a strong algorithm (e.g., bcrypt, Argon2)? |
| &nbsp;⚠️&nbsp;<br><sup><a id="note6-origin">[note 6](#note6)</a></sup> | Are data backup and recovery processes GDPR-compliant? |
| &nbsp;✅&nbsp; | Is personal data stored in data centers located within the EU? |

---

| **Result** | **Data anonymization and pseudonymization** |
| :----: | :--- |
| &nbsp;❌&nbsp;<br><sup><a id="note7-origin">[note 7](#note7)</a></sup> | Is personal data anonymized where possible? |
| &nbsp;❌&nbsp;<br><sup><a id="note7-origin">[note 7](#note7)</a></sup> | Are pseudonymization techniques used to protect data while maintaining its utility? |

---

| **Result** | **Data subject rights** |
| :----: | :--- |
| &nbsp;❌&nbsp; | Can users download or request all personal data related to them (data access request)? |
| &nbsp;❌&nbsp; | Is there an interface or process for users to request the deletion of their personal data? |
| &nbsp;❌&nbsp; | Can users withdraw their consent for data processing? |

---

| **Result** | **Documentation and communication** |
| :----: | :--- |
| &nbsp;❌&nbsp;<br><sup><a id="note8-origin">[note 8](#note8)</a></sup> | Is there a privacy policy available to users during registration and easily accessible? |
| &nbsp;❌&nbsp; | Are administrators and developers provided with documented data protection practices <br>and processing activities? |
| &nbsp;❌&nbsp; | Is there a documented data breach response process (e.g., how to notify authorities <br>and users of a breach)? |

---

**Symbols used:**  
✅ Pass (a note can be added)  
❌ Fail (a note can be added)  
⚠️ Attention (a note can be added)

## Notes
*Click the note to return to the relevant checklist item.*

1. <a id="note1">[Other personal data (email, birthdate) are named in the registration form, but the system also logs the user's IP address together with the user token when logging in.](#note1-origin)</a> 
2. <a id="note2">[Users can view some of their data (email, role, terms accepted, role) in their account, but some is missing (birthdate, logged IP) and none of the data can be edited or deleted by the user.](#note2-origin)</a> 
3. <a id="note3">[Reservers can add and modify reservations, only administrators can remove them.](#note3-origin)</a> 
4. <a id="note4">[Login form data is sent to the server unencrypted.](#note4-origin)</a> 
5. <a id="note5">[A ZAP scan still warns about a possible SQL injection.](#note5-origin)</a> 
6. <a id="note6">[Backup and recovery processes not known.](#note6-origin)</a> 
7. <a id="note7">[Uncertain if any of the personal data collected can be anonymized/pseudonymized, possibly the birth date.](#note7-origin)</a> 
8. <a id="note8">[A link to a privacy policy page is easily available, but the page itself is blank.](#note8-origin)</a> 
