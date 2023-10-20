---
layout: default
title: Travel Impact Model
permalink: /

secretariat:
  - name: International Council on Clean Transportation
    contact: Dr. Dan Rutherford
    role: Aviation Program Director
    url: https://www.theicct.org

advisory_commitee_members:
  - name: American Airlines
    contact: Jill Blickstein
    role: Vice President, Sustainability
    url: https://www.aa.com
  - name: Aviation Environment Federation
    contact: Tim Johnson
    role: Director
    url: https://www.aef.org.uk
  - name: easyJet
    contact: Jane Ashton
    role: Sustainability Director
    url: https://www.easyjet.com
  - name: European Union Aviation Safety Agency
    contact: Achilleas Achilleos *
    role: Strategic Programme Officer
    url: https://www.easa.europa.eu
  - name: Federal Aviation Administration
    contact: Kevin Welsh *
    role: Executive Director, Environment & Energy
    url: https://www.faa.gov
  - name: Imperial College London
    contact: Dr. Marc Stettler
    role: Reader in Transport and Environment
    url: https://www.imperial.ac.uk
  - name: Lufthansa Group
    contact: Caroline Drischel
    role: Head of Corporate Responsibility
    url: http://www.dlh.de
  - name: Massachusetts Institute of Technology
    contact: Prof. Steven Barrett
    role: Professor of Aeronautics and Astronautics
    url: https://www.mit.edu
  - name: Rocky Mountain Institute
    contact: Andrew Chen
    role: Principal, Aviation Decarbonization
    url: https://www.rmi.org
  - name: Travalyst
    contact: Sally Davey
    role: Chief Executive Officer
    url: https://www.travalyst.org
---

# Travel Impact Model

The Travel Impact Model (TIM) is a transparent & continuously improving emissions estimation model that is built from public and licensable external datasets, based on the latest science. It aims to provide a
single source of truth, as a public good, for calculating and presenting the climate impact of individual flight trips to passengers.

## About the model

The model combines flight origin and destination, aircraft type, cabin class and seat configuration, load factors and average aircraft utilization to estimate CO2 emissions for each flight
(per seat/passenger). The methodology output is free and available publicly via an API. More granular methodology and API access details can be found <a href="https://github.com/google/travel-impact-model" aria-label="More granular methodology and API access details" target="_blank">here</a>.

### Model principles

<ul>
  <li class="principle">
    <b>Accurate</b> and validated with real-world data
  </li>
  <li class="principle">
    <b>Precise</b> in distinguishing more and less emitting flights
  </li>
  <li class="principle">
    <b>Comprehensive</b> in covering the full climate impacts of aviation
  </li>
  <li class="principle">
    <b>Futureproof</b> across new technologies and aircraft designs
  </li>
  <li class="principle">
    <b>Transparent</b> in methods, data sources, and assumptions
  </li>
  <li class="principle">
    <b>Consistent</b> across airlines and industry stakeholders
  </li>
  <li class="principle">
    <b>Accessible</b> and free to all users
  </li>
</ul>

## Governance

The Travel Impact Model is administered by Google and overseen by an independent Advisory Committee that consists of world-leading experts on sustainability and aviation from industry, academia,
policy and NGOs. The Advisory Committee is accompanied by a Secretariat that provides technical expertise based on scientific evidence. The Advisory Committee together with the Secretariat
ensures that the Travel Impact Model continues to evolve as a public good, and future development of the model is executed with high rigor, integrity, speed and according to the latest science.

### Secretariat

{% for x in page.secretariat %}
<div class="name">{{ x.contact }}</div>
<div class="role">{{ x.role }}</div>
<div>
  <a href="{{ x.url }}" target="_blank" class="url">{{ x.name }}</a>
</div>
{% endfor %}

### Advisory committee members

<div class="institutions">
  {% for x in page.advisory_commitee_members %}
  <div class="institution">
    <div class="name">{{ x.contact }}</div>
    <div class="role">{{ x.role }}</div>
    <div>
      <a href="{{ x.url }}" target="_blank" class="url">{{ x.name }}</a>
    </div>
  </div>
  {% endfor %}
</div>

<p class="footnote">
  * Non-voting observer
</p>
