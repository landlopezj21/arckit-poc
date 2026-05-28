# Jurisdicciones

ArcKit incluye un baseline del Gobierno del Reino Unido más overlays contribuidos por la comunidad para otras jurisdicciones. Los comandos comunitarios están marcados con `[COMMUNITY]` en la referencia oficial.

---

## 🇬🇧 UK Government Core

**17 comandos oficiales**

Marco de referencia: GDS Service Standard, Technology Code of Practice (TCoP), Secure by Design, MOD JSP 936, HM Treasury Green & Orange Books, G-Cloud, DOS procurement, AI Playbook, ATRS.

Instalación: incluido en el core plugin `arckit`.

---

## 🌐 Genérico / Cross-jurisdiccional

**54 comandos**

Fundamentos agnósticos de jurisdicción: requisitos, ADRs, Wardley Mapping, DevOps / MLOps / FinOps, trazabilidad, conformidad, evaluación de proveedores.

Instalación: incluido en el core plugin `arckit`.

---

## 🇪🇺 EU Regulatory

**7 comandos — comunidad**

Marcos cubiertos: GDPR, EU AI Act, NIS2, DORA, Cyber Resilience Act, Digital Services Act, Data Act.

```bash
claude plugin install arckit arckit-eu
```

---

## 🇫🇷 Francia

**12 comandos — comunidad**

Marcos cubiertos: ANSSI Guide d'hygiène, SecNumCloud 3.2, EBIOS Risk Manager, DINUM (RGI / RGAA / RGS / RGESN), CNIL RGPD, Diffusion Restreinte, code de la commande publique.

```bash
claude plugin install arckit arckit-fr
```

---

## 🇦🇹 Austria

**3 comandos — comunidad**

Marcos cubiertos: NISG (transposición NIS2), DSG / DSGVO, Bundesvergabegesetz 2018.

```bash
claude plugin install arckit arckit-at
```

---

## 🇨🇦 Canada Federal

**12 comandos — comunidad**

Marcos cubiertos: FITAA (C-70), PIA, ATIP, Algorithmic Impact Assessment, Charter, SOIA, GC Digital Standards, cloud residency, Official Languages Act, OCAP, PSPC procurement.

```bash
claude plugin install arckit arckit-ca
```

---

## 🇦🇪 UAE Federal

**12 comandos — comunidad**

Marcos cubiertos: PDPL, IAS controls, sovereign cloud residency, UAE Pass, Smart Data classification, AI Charter, autonomy tier, federal procurement, digital records.

```bash
claude plugin install arckit arckit-uae
```

---

## 🇦🇺 Australian Federal

**8 comandos — comunidad**

Marcos cubiertos: ASD Essential Eight, Information Security Manual, DTA Digital Service Standard, Privacy Act 1988 PIA, OAIC Notifiable Data Breach playbook, PSPF, DTA AI Assurance, DISP supplier attestation.

```bash
claude plugin install arckit arckit-au
```

---

## 🇺🇸 USA Federal Civilian

**10 comandos — comunidad**

Marcos cubiertos: FedRAMP, FISMA / NIST 800-53 Rev 5, CISA Zero Trust Maturity, OMB M-19-17 ICAM, NIST AI RMF, OMB M-24-10/M-25-21 AI assurance, E-Gov §208 PIA, EO 14028 SBOM.

```bash
claude plugin install arckit arckit-us
```

---

## 🏦 UK Finance (sector)

**Comunidad — slice de pagos**

Marcos cubiertos: PSD2 SCA-RTS (PSRs 2017), EMI / PI safeguarding (EMR 2011), FCA Consumer Duty (PS22/9), Critical Third Parties (PS24/16).

Audiencia: arquitectos en PSPs, EMIs y PIs del Reino Unido.

---

## 🩺 UK NHS (sector)

**4 comandos — comunidad**

Marcos cubiertos: NHS DCB0129 / DCB0160 Clinical Safety Case, NHS DTAC v3, UK MDR 2002 + EU MDR 2017/745 (SaMD / AIaMD).

---

## Instalar todos los overlays

```bash
claude plugin install arckit arckit-uae arckit-fr arckit-ca arckit-eu arckit-at arckit-au arckit-us
```

O en forma abreviada:

```bash
claude plugin install arckit arckit-{uae,fr,ca,eu,at,au,us}
```
