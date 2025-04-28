
***XML

- **Whitespace Characters**: XML defines which characters count as whitespace (e.g., space, tab, newline). Characters like **EBCDIC 'NEL'** are **not valid** as whitespace and should be avoided.

- **Unsupported Characters**: If your XML document uses a charset like **ISO-Latin-1** and you want to include characters outside of it (e.g., Greek letters), use **character references**:
  - Example: `&#9824;` → Displays the **spade (♠)** symbol, which is the **9824th Unicode character**.

- **Binary Data**: Must be **converted to printable characters** (e.g., using **Base64 encoding**) before including in XML, since XML supports only text content.

