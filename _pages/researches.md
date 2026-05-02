---
layout: page
permalink: /researches/
title: Research
nav: true
nav_order: 3
description: >
  Publications and working papers.
---

<!-- _pages/researches.md -->

<style>
/* Clean bibliography numbering */
.bib-section {
  counter-reset: bib-counter;
}
.bib-section ol.bibliography {
  list-style: none;
  padding-left: 0;
}
.bib-section ol.bibliography > li {
  counter-increment: bib-counter;
  position: relative;
  padding-left: 2.2rem;
  margin-bottom: 1.2rem;
}
.bib-section ol.bibliography > li::before {
  content: "[" counter(bib-counter) "]";
  position: absolute;
  left: 0;
  top: 0;
  font-size: 0.88rem;
  color: #999;
  font-weight: 500;
}

/* Year group headings */
.bib-section h2.bibliography {
  font-size: 1.05rem;
  font-weight: 600;
  color: #555;
  margin: 1rem 0 0.5rem 0;
  border-bottom: 1px solid #eee;
  padding-bottom: 0.25rem;
}

/* Working Papers: hide year headings */
.bib-no-year h2.bibliography {
  display: none;
}

/* Entry internal spacing */
.bib-clean-entry {
  /* no extra wrapper needed */
}

/* Abstract toggle */
.bib-clean-abstract-toggle {
  color: #6c757d !important;
  text-decoration: none !important;
  font-size: 0.8rem;
}
.bib-clean-abstract-toggle:hover {
  color: #007bff !important;
}
.bib-clean-abstract {
  margin-left: 0;
}
</style>

<script>
document.addEventListener('DOMContentLoaded', function() {
  document.querySelectorAll('.bib-clean-abstract-toggle').forEach(function(toggle) {
    toggle.addEventListener('click', function() {
      var abstract = this.closest('.bib-clean-entry').querySelector('.bib-clean-abstract');
      if (abstract) {
        if (abstract.style.display === 'none' || abstract.style.display === '') {
          abstract.style.display = 'block';
          this.textContent = '[Hide]';
        } else {
          abstract.style.display = 'none';
          this.textContent = '[Abstract]';
        }
      }
    });
  });
});
</script>

---

<div class="bib-section" markdown="1">

## English Journal Articles / 英文学术期刊论文

{% bibliography --template bib_clean -f publications_english %}

</div>

<div class="bib-section" markdown="1">

## Chinese Journal Articles / 中文学术期刊论文

{% bibliography --template bib_clean -f publications %}

</div>

<div class="bib-section bib-no-year" markdown="1">

## Working Papers / 工作论文

{% bibliography --template bib_clean -f working_papers %}

</div>

