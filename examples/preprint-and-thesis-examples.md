# Academic Metadata Examples: Preprints, Conferences & Dissertations

---

## 1. Preprint / Working Paper (arXiv / bioRxiv / SSRN Style)

### HTML Meta Tags (`<head>`)
```html
<meta name="citation_title" content="Diffusion Models for Ab Initio De Novo Antibody Design">
<meta name="citation_author" content="Chen, Wei-Lun">
<meta name="citation_author_institution" content="Department of Bioengineering, UC Berkeley">
<meta name="citation_author_orcid" content="https://orcid.org/0000-0003-4567-8901">
<meta name="citation_date" content="2026/03/24">
<meta name="citation_technical_report_number" content="arXiv:2603.99887">
<meta name="citation_technical_report_institution" content="arXiv">
<meta name="citation_pdf_url" content="https://arxiv.org/pdf/2603.99887.pdf">
<meta name="citation_abstract_html_url" content="https://arxiv.org/abs/2603.99887">
<meta name="citation_doi" content="10.48550/arXiv.2603.99887">

<!-- Dublin Core -->
<meta name="DC.title" content="Diffusion Models for Ab Initio De Novo Antibody Design">
<meta name="DC.creator" content="Chen, Wei-Lun">
<meta name="DC.issued" scheme="W3CDTF" content="2026-03-24">
<meta name="DC.description.abstract" xml:lang="en" content="We present a 3D equivariant diffusion framework for generating therapeutic antibodies targeting antigen epitopes...">
<meta name="DC.identifier.doi" content="10.48550/arXiv.2603.99887">
<meta name="DC.type" content="Preprint">
<meta name="DC.type" content="ScholarlyArticle">
<meta name="DC.format" content="application/pdf">
```

### Schema.org JSON-LD (`@graph`)
```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "ScholarlyArticle",
      "@id": "https://arxiv.org/abs/2603.99887#article",
      "headline": "Diffusion Models for Ab Initio De Novo Antibody Design",
      "name": "Diffusion Models for Ab Initio De Novo Antibody Design",
      "description": "A 3D equivariant diffusion framework for generating therapeutic antibodies targeting antigen epitopes.",
      "abstract": "We present a 3D equivariant diffusion framework for generating therapeutic antibodies targeting antigen epitopes with atomic complementarity. Validated with surface plasmon resonance binding assays, generated CDR-H3 loops show nanomolar target engagement across SARS-CoV-2 and Oncology targets.",
      "datePublished": "2026-03-24",
      "dateModified": "2026-03-24",
      "isAccessibleForFree": true,
      "license": "https://creativecommons.org/licenses/by/4.0/",
      "mainEntityOfPage": {
        "@type": "WebPage",
        "@id": "https://arxiv.org/abs/2603.99887"
      },
      "author": [
        {
          "@type": "Person",
          "name": "Wei-Lun Chen",
          "identifier": "https://orcid.org/0000-0003-4567-8901",
          "affiliation": {
            "@type": "Organization",
            "name": "University of California, Berkeley",
            "sameAs": "https://ror.org/01an7q238"
          }
        }
      ],
      "publisher": {
        "@type": "Organization",
        "name": "arXiv",
        "url": "https://arxiv.org",
        "sameAs": "https://www.wikidata.org/wiki/Q118398"
      },
      "encoding": [
        {
          "@type": "MediaObject",
          "encodingFormat": "application/pdf",
          "contentUrl": "https://arxiv.org/pdf/2603.99887.pdf"
        }
      ],
      "identifier": [
        {
          "@type": "PropertyValue",
          "propertyID": "doi",
          "value": "10.48550/arXiv.2603.99887"
        },
        {
          "@type": "PropertyValue",
          "propertyID": "arxiv",
          "value": "2603.99887"
        }
      ]
    }
  ]
}
```

---

## 2. University Repository / Ph.D. Dissertation

### HTML Meta Tags (`<head>`)
```html
<meta name="citation_title" content="Provably Secure Multi-Party Quantum Cryptography in Distributed Networks">
<meta name="citation_author" content="O'Connor, Liam Patrick">
<meta name="citation_author_orcid" content="https://orcid.org/0000-0002-7711-2233">
<meta name="citation_dissertation_institution" content="University of Oxford">
<meta name="citation_dissertation_name" content="Ph.D. Thesis in Quantum Information Theory">
<meta name="citation_publication_date" content="2026/06/10">
<meta name="citation_pdf_url" content="https://ora.ox.ac.uk/objects/uuid:12345-67890/files/thesis.pdf">
<meta name="citation_abstract_html_url" content="https://ora.ox.ac.uk/objects/uuid:12345-67890">
<meta name="citation_doi" content="10.5287/ora-123456">

<!-- Dublin Core -->
<meta name="DC.title" content="Provably Secure Multi-Party Quantum Cryptography in Distributed Networks">
<meta name="DC.creator" content="O'Connor, Liam Patrick">
<meta name="DC.issued" scheme="W3CDTF" content="2026-06-10">
<meta name="DC.publisher" content="University of Oxford">
<meta name="DC.identifier.doi" content="10.5287/ora-123456">
<meta name="DC.type" content="Thesis">
<meta name="DC.type" content="ScholarlyArticle">
<meta name="DC.format" content="application/pdf">
<meta name="DC.rights" content="https://creativecommons.org/licenses/by-nc-nd/4.0/">
```

### Schema.org JSON-LD (`@graph`)
```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "Thesis",
      "@id": "https://ora.ox.ac.uk/objects/uuid:12345-67890#thesis",
      "headline": "Provably Secure Multi-Party Quantum Cryptography in Distributed Networks",
      "name": "Provably Secure Multi-Party Quantum Cryptography in Distributed Networks",
      "description": "Doctoral dissertation examining quantum key distribution protocols and composable multi-party computation.",
      "abstract": "This dissertation establishes novel security proofs for quantum key distribution (QKD) under universal composability frameworks in noisy, uncalibrated fiber networks...",
      "datePublished": "2026-06-10",
      "dateModified": "2026-06-10",
      "inLanguage": "en",
      "isAccessibleForFree": true,
      "license": "https://creativecommons.org/licenses/by-nc-nd/4.0/",
      "author": {
        "@type": "Person",
        "name": "Liam Patrick O'Connor",
        "identifier": "https://orcid.org/0000-0002-7711-2233",
        "alumniOf": {
          "@type": "Organization",
          "name": "University of Oxford",
          "sameAs": "https://ror.org/052gg0110"
        }
      },
      "sourceOrganization": {
        "@type": "Organization",
        "name": "University of Oxford",
        "sameAs": "https://ror.org/052gg0110"
      },
      "publisher": {
        "@type": "Organization",
        "name": "Oxford University Research Archive (ORA)",
        "url": "https://ora.ox.ac.uk"
      },
      "encoding": [
        {
          "@type": "MediaObject",
          "encodingFormat": "application/pdf",
          "contentUrl": "https://ora.ox.ac.uk/objects/uuid:12345-67890/files/thesis.pdf"
        }
      ],
      "identifier": [
        {
          "@type": "PropertyValue",
          "propertyID": "doi",
          "value": "10.5287/ora-123456"
        }
      ]
    }
  ]
}
```
