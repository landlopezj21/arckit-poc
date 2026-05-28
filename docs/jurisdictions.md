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

## 🇨🇱 Chile — guía de uso sin overlay oficial

ArcKit **no cuenta aún con un overlay oficial para Chile**, pero existen marcos normativos locales que todo arquitecto debe considerar al diseñar sistemas en el país.

### Marco normativo aplicable

| Marco | Descripción | Aplicabilidad |
|---|---|---|
| **Ley 21.663 — Ley Marco de Ciberseguridad (2024)** | Establece obligaciones para operadores de servicios esenciales e infraestructura crítica. Crea la Agencia Nacional de Ciberseguridad (ANCI). | Obligatoria para sistemas críticos y servicios esenciales |
| **Ley 19.628 — Protección de Datos Personales** | Marco vigente de tratamiento de datos personales. Actualmente en proceso de modernización. | Obligatoria para sistemas que traten datos personales |
| **Estándares de la Secretaría de Gobierno Digital** | Normas de interoperabilidad, seguridad y accesibilidad para sistemas del Estado chileno. | Obligatoria para proyectos del sector público |
| **NIST Cybersecurity Framework** | Referencia técnica ampliamente adoptada en Chile tanto en sector público como privado. | Recomendada |

### Estrategia recomendada con ArcKit hoy

Dado que no existe `arckit-cl`, la aproximación más efectiva es combinar overlays existentes:

```bash
# Base genérica + overlay UE como referencia para protección de datos
claude plugin install arckit arckit-eu
```

El overlay `arckit-eu` cubre GDPR, que es el modelo en que se basa la futura ley de datos personales chilena, por lo que sus artefactos (DPIA, registros de tratamiento, análisis de base legal) son directamente adaptables al contexto local.

### Artefactos clave a generar para proyectos en Chile

```
/arckit.risk          # Registro de riesgos — adaptar a amenazas según Ley 21.663
/arckit.dpia          # Evaluación de impacto en protección de datos (Ley 19.628)
/arckit.secure-by-design  # Diseño seguro alineado a controles ANCI
/arckit.requirements  # Incluir requisitos de residencia de datos y soberanía
```

### Contribuir un overlay `arckit-cl`

ArcKit acepta contribuciones comunitarias de nuevas jurisdicciones. Si quieres desarrollar un overlay oficial para Chile que cubra la Ley 21.663, Ley 19.628 y los estándares de la Secretaría de Gobierno Digital, puedes seguir el modelo de cualquier overlay existente:

- Repositorio: [github.com/tractorjuice/arc-kit](https://github.com/tractorjuice/arc-kit)
- Guía de contribución: `CONTRIBUTING.md` en el repositorio
- Comunidad: [discord.gg/JqgjQSnD](https://discord.gg/JqgjQSnD)

---

## Instalar todos los overlays

```bash
claude plugin install arckit arckit-uae arckit-fr arckit-ca arckit-eu arckit-at arckit-au arckit-us
```

O en forma abreviada:

```bash
claude plugin install arckit arckit-{uae,fr,ca,eu,at,au,us}
```
