# Google Scholar & Highwire Press Meta Tags Reference

Based on official specifications from [Google Scholar Inclusion Guidelines](https://scholar.google.com/intl/en/scholar/inclusion.html#indexing).

---

## 1. Core Bibliographic Tags

| Tag Name | Required / Recommended | Format / Example | Description |
| :--- | :--- | :--- | :--- |
| `citation_title` | **Required** | `A Fast Algorithm for Nearest Neighbors` | Complete, exact title of the paper. Do NOT include journal name or site name. |
| `citation_author` | **Required** | `Knuth, Donald E.` or `Donald E. Knuth` | Author name. **Must repeat this tag for each author** in authorship order. |
| `citation_publication_date` | **Required** | `2026/04/15` or `2026/04` or `2026` | Formal publication date. Slashes required if year/month/day. |
| `citation_pdf_url` | **Critical for Full-Text Indexing** | `https://example.org/papers/2026/p123.pdf` | Direct, absolute URL to the full-text PDF file. |
| `citation_journal_title` | Required for Journal Papers | `Journal of Machine Learning Research` | Full title of the journal. |
| `citation_journal_abbrev` | Optional | `J. Mach. Learn. Res.` | ISO / standard journal title abbreviation. |
| `citation_volume` | Recommended | `27` | Journal volume number. |
| `citation_issue` | Recommended | `4` | Journal issue number. |
| `citation_firstpage` | Recommended | `101` | First page number of the article. |
| `citation_lastpage` | Recommended | `135` | Last page number of the article. |
| `citation_doi` | Recommended | `10.1145/123456.789012` | Digital Object Identifier without `https://doi.org/` prefix. |
| `citation_issn` | Recommended | `1532-4435` | ISSN of the publishing journal. |
| `citation_isbn` | For Books / Monographs | `978-0-262-03384-8` | ISBN for book chapters / books. |
| `citation_publisher` | Recommended | `MIT Press` | Academic publisher or institutional press. |
| `citation_abstract_html_url` | Recommended | `https://example.org/articles/p123` | Canonical URL of the HTML abstract page. |
| `citation_fulltext_html_url` | Optional | `https://example.org/articles/p123/full` | Direct URL to the HTML full text version. |
| `citation_language` | Optional | `en`, `fr`, `de`, `id` | Primary language of the manuscript. |
| `citation_keywords` | Optional | `machine learning; graph neural networks; clustering` | Semicolon or comma-separated keywords. |

---

## 2. Author Disambiguation & Affiliation Tags

| Tag Name | Format / Example | Description |
| :--- | :--- | :--- |
| `citation_author_institution` | `Department of Computer Science, Stanford University` | Institutional affiliation corresponding to the preceding `citation_author`. |
| `citation_author_orcid` | `https://orcid.org/0000-0002-1825-0097` | ORCID identifier URI for author entity disambiguation. |
| `citation_author_email` | `author@stanford.edu` | Corresponding author email address. |

---

## 3. Document-Type Specific Tags

### A. Conference Proceedings
```html
<meta name="citation_title" content="Attention Is All You Need">
<meta name="citation_author" content="Vaswani, Ashish">
<meta name="citation_conference_title" content="Advances in Neural Information Processing Systems 30 (NIPS 2017)">
<meta name="citation_conference_place" content="Long Beach, CA, USA">
<meta name="citation_conference_date" content="2017/12/04-2017/12/09">
<meta name="citation_firstpage" content="5998">
<meta name="citation_lastpage" content="6008">
<meta name="citation_pdf_url" content="https://proceedings.neurips.cc/paper/2017/file/3f5ee243547dee91fbd053c1c4a845aa-Paper.pdf">
```

### B. Preprints, Working Papers & Technical Reports
```html
<meta name="citation_title" content="Generative Agent Simulations of Human Behavior">
<meta name="citation_author" content="Park, Joon Sung">
<meta name="citation_technical_report_number" content="arXiv:2304.03442">
<meta name="citation_technical_report_institution" content="arXiv">
<meta name="citation_date" content="2023/04/07">
<meta name="citation_pdf_url" content="https://arxiv.org/pdf/2304.03442.pdf">
```

### C. Master's Theses & PhD Dissertations
```html
<meta name="citation_title" content="Scalable Quantum Circuit Compilation and Verification">
<meta name="citation_author" content="Alexander, Sarah M.">
<meta name="citation_dissertation_institution" content="Massachusetts Institute of Technology">
<meta name="citation_dissertation_name" content="Ph.D. Dissertation">
<meta name="citation_publication_date" content="2026/05/20">
<meta name="citation_pdf_url" content="https://dspace.mit.edu/bitstream/handle/1721.1/123456/thesis.pdf">
```

---

## 4. Bibliographic Citation References

To assist Google Scholar and AI engines in extracting reference lists without PDF parsing errors, you can include machine-readable `citation_reference` meta tags:

```html
<meta name="citation_reference" content="citation_title=Attention Is All You Need; citation_author=Vaswani, A.; citation_publication_date=2017; citation_conference_title=NIPS 2017;">
<meta name="citation_reference" content="citation_title=Deep Residual Learning for Image Recognition; citation_author=He, K.; citation_publication_date=2016; citation_doi=10.1109/CVPR.2016.90;">
```

---

## 5. Webmaster & Crawl Best Practices

1. **PDF File Accessibility**: The PDF file must be reachable by Googlebot without cookie requirements, dynamic token expirations, CAPTCHAs, or IP geoblocking.
2. **First Page Layout**: In the PDF file, the title should be in a prominent font at the top of page 1, followed immediately by authors, and end with a section header titled `References` or `Bibliography`.
3. **Link Depth**: All paper URLs should be discoverable within **10 HTML links** from the homepage.
4. **Abstract Free Visibility**: Do not use modals or requiring user registration to view the abstract. Google Scholar flags and excludes sites showing login screens for search clicks.
