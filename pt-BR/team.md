---
layout: pt-BR/default
title: O time Rust &middot; A linguagem de programação Rust

# map from GH username to name & irc nick (irc nick can be omitted if it
# matches GH).
people:
  aatch:
    name: James Miller
  arielb1:
    name: Ariel Ben-Yehuda
  alexcrichton:
    name: Alex Crichton
    irc: acrichto
  aturon:
    name: Aaron Turon
  bkoropoff:
    name: Brian Koropoff
  brson:
    name: Brian Anderson
  bstrie:
    name: Ben Striegel
  BurntSushi:
    name: Andrew Gallant
    irc: burntsushi
  carols10cents:
    name: Carol Nichols
  dotdash:
    name: Björn Steinbrink
    irc: doener
  eddyb:
    name: Eduard Burtescu
  edunham:
    name: Emily Dunham
  erickt:
    name: Erick Tryzelaar
  Gankro:
    name: Alexis Beingessner
    ex-teams: ["libs"]
  huonw:
    name: Huon Wilson
    irc: huon
    ex-teams: ["core", "lang", "libs"]
  GuillaumeGomez:
    name: Guillaume Gomez
    irc: imperio
  jonathandturner:
    name: Jonathan Turner
    irc: jntrnr
  jseyfried:
    name: Jeffrey Seyfried
    irc: jseyfried
  Kimundi:
    name: Marvin Löbel
    irc: kimundi
  manishearth:
    name: Manish Goregaokar
    irc: Manishearth
  mbrubeck:
    name: Matt Brubeck
  michaelwoerister:
    name: Michael Woerister
    irc: mw
  niconii:
    name: Nicolette Verlinden
    irc: niconii
  nikomatsakis:
    name: Niko Matsakis
    irc: nmatsakis
  nrc:
    name: Nick Cameron
  pcwalton:
    name: Patrick Walton
  peschkaj:
    name: Jeremiah Peschka
    irc: peschkaj
  pnkfelix:
    name: Felix Klock
  sfackler:
    name: Steven Fackler
  skade:
    name: Florian Gilcher
  steveklabnik:
    name: Steve Klabnik
  vadimcn:
    name: Vadim Chugunov
  wycats:
    name: Yehuda Katz
  jonathandturner:
    name: Jonathan Turner
  badboy:
    name: Jan-Erik Rediger
  johannhof:
    name: Johann Hofmann
  booyaa:
    name: Mark Sta Ana

# Information about each team. Omit `lead` for teams without leaders.
teams:
  - name: Time central
    responsibility: "direção geral do projeto, liderança de subtimes, outras preocupações"
    members: [brson, alexcrichton, wycats, steveklabnik, nikomatsakis, aturon, pcwalton, erickt]
  - name: Time de design da linguagem
    responsibility: "pensa em novas features para a linguagem"
    members: [eddyb, nrc, pnkfelix, nikomatsakis, aturon]
    lead: nikomatsakis
  - name: Time de bibliotecas
    responsibility: "a biblioteca padrão de Rust, crates da rust-lang, padrões"
    members: [brson, alexcrichton, sfackler, BurntSushi, Kimundi, aturon]
    lead: aturon
  - name: Time do compilador
    responsibility: "internos do compilador, optimizações"
    members: [arielb1, eddyb, nrc, pnkfelix, bkoropoff, nikomatsakis, aatch, dotdash, michaelwoerister, jseyfried]
    lead: nikomatsakis
  - name: Ferramentas e infraestrutura
    responsibility: "suporte de ferramentas (ex.: Cargo, rustup), Infraestrutura CI, etc."
    members: [brson, nrc, alexcrichton, vadimcn, wycats, michaelwoerister]
    lead: alexcrichton
  - name: Time da comunidade
    responsibility: "coordenar eventos, propaganda, usuários comerciais, materiais de ensino e exposição"
    lead: erickt
    members: [brson, skade, manishearth, johannhof, steveklabnik, carols10cents, badboy, booyaa, bstrie, erickt, jonathandturner, edunham]
    email: community-team@rust-lang.org
  - name: Time da documentação
    responsibility: "se certificam de que Rust possui uma incrível documentação"
    members: [steveklabnik, GuillaumeGomez, jonathandturner, peschkaj]
  - name: Time da moderação
    responsibility: "mantêm firme o <a href='https://www.rust-lang.org/conduct.html'>codigo de conduta</a>"
    members: [mbrubeck, BurntSushi, manishearth, pnkfelix, niconii]
    email: rust-mods@rust-lang.org
  - name: Time Rust alumni
    responsibility: "curtir um calmo retiro"
    members: [Gankro, huonw]

# Information on sites to get profile information from
sites:
  github:
    url: https://github.com/%nick
    avatar: https://avatars.githubusercontent.com/%nick
  twitter:
    url: https://twitter.com/%nick
    avatar: https://avatars.io/twitter/%nick?size=large
---

<style type="text/css">
.headshot {
  border: 1px solid #888;
  width: 140px;
}

.person {
  display: inline-block;
  position: relative;
  margin-bottom: 20px;
}
.lead { font-weight: bold; }
.lead .name::after { content: " (lead)"; }
.details {
  display: none;
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  background: rgba(0, 0, 0, 0.5);
  color: white;
  font-weight: normal;
}
.person:hover .details {
   display: block;
}

.headshots {
  text-align: center;
  margin: 0px auto;
  padding: 0;
  width: 700px;
  max-width: 100%;
  list-style: none;
}
</style>

# O Time Rust

O projeto Rust é [governado](https://github.com/rust-lang/rfcs/blob/master/text/1068-rust-governance.md)
por inúmeros times, cada um focado em uma área específica. Abaixo estão eles, em ordem alfabética.

Para contactar um time, poste sua pergunta ou comentário no [Fórum dos Internos](https://internals.rust-lang.org/) e
rotule a sua questão com a categoria que possui o nome do time. Note que revelações de falhas de segurança
devem seguir o [Processo de revelação de falhas de Segurança](security.html).

{% for team in page.teams %}
<section id="{{ team.name | replace:' ','-' }}">
<h2> {{ team.name }} </h2>

<strong>Responsabilidade</strong>: <em>{{ team.responsibility }}</em>

<br />

{% if team.email %}
  <strong>Contact</strong>:
  <a href="mailto:{{ team.email | uri_escape }}">{{ team.email }}</a>
{% endif %}

<ul class="headshots">
{% for nick in team.members %}
  {% assign person = page.people[nick] %}
  {% if person.site %}
    {% assign sitename = person.site %}
  {% else %}
    {% assign sitename = "github" %}
  {% endif %}
  {% assign site = page.sites[sitename] %}
  <li class="person {% if team.lead and team.lead == nick %}lead{% endif %}">
  <a href="{{ site.url | replace:'%nick',nick }}">
    <div class="name">{{ person.name }}</div>
    <div class="details">
      <div>irc: {% if person.irc %}{{ person.irc }}{% else %}{{ nick }}{% endif %}</div>
      {% if person.ex-teams %}
      <div>teams: {{ person.ex-teams | join: ", " }}</div>
      {% endif %}
    </div>
    <img class="headshot" src="{{ site.avatar | replace:'%nick',nick }}" alt="{{ person.name }}">
  </a>
</li>
{% endfor %}
</ul>
</section>
{% endfor %}
