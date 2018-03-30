---
layout: single
permalink: /people
title: ""
classes: wide
authors:
    - author0
    - author1
---
{% assign authorCount = page.authors | size %}
{% if authorCount == 0 %}
  {% if page.author and site.data.authors[page.author] %}
    {% assign author = site.data.authors[page.author] %}
  {% else %}
    {% assign author = site.author %}
  {% endif %}
  
  {% assign authors = {{author.authorid | split: "," }} %}
{% else %}
  {% assign authors = page.authors %}
{% endif %}

<div itemscope itemtype="http://schema.org/Person">
  {% for authorid in authors %}
  <p>
    {% if site.data.authors[authorid].avatar %}
      <div class="author__avatar">
        {% if site.data.authors[authorid].avatar contains "://" %}
          <img src="{{ site.data.authors[authorid].avatar }}" alt="{{ site.data.authors[authorid].name }}" itemprop="image">
        {% else %}
          <img src="{{ site.data.authors[authorid].avatar | absolute_url }}" class="author__avatar" alt="{{ site.data.authors[authorid].name }}" itemprop="image">
        {% endif %}
      </div>
    {% endif %}

    <div class="author__content">
      <h3 class="author__name" itemprop="name">{{ site.data.authors[authorid].name }}</h3>
      {% if site.data.authors[authorid].bio %}
        <p class="author__bio" itemprop="description">
          {{ site.data.authors[authorid].bio }}
        </p>
      {% endif %}
    </div>

    <div class="author__urls-wrapper">
      <button class="btn btn--inverse">{{ site.data.ui-text[site.locale].follow_label | remove: ":" | default: "Follow" }}</button>
      <ul class="author__urls social-icons">
        {% if site.data.authors[authorid].location %}
          <li itemprop="homeLocation" itemscope itemtype="http://schema.org/Place">
            <i class="fa fa-fw fa-map-marker" aria-hidden="true"></i> <span itemprop="name">{{ site.data.authors[authorid].location }}</span>
          </li>
        {% endif %}

        {% if site.data.authors[authorid].uri %}
          <li>
            <a href="{{ site.data.authors[authorid].uri }}" itemprop="url">
              <i class="fa fa-fw fa-chain" aria-hidden="true"></i> {{ site.data.ui-text[site.locale].website_label | default: "Website" }}
            </a>
          </li>
        {% endif %}

        {% if site.data.authors[authorid].email %}
          <li>
            <a href="mailto:{{ site.data.authors[authorid].email }}">
              <meta itemprop="email" content="{{ site.data.authors[authorid].email }}" />
              <i class="fa fa-fw fa-envelope-square" aria-hidden="true"></i> {{ site.data.ui-text[site.locale].email_label | default: "Email" }}
            </a>
          </li>
        {% endif %}

        {% if site.data.authors[authorid].keybase %}
          <li>
            <a href="https://keybase.io/{{ site.data.authors[authorid].keybase }}" itemprop="sameAs">
              <i class="fa fa-fw fa-key" aria-hidden="true"></i> Keybase
            </a>
          </li>
        {% endif %}

        {% if site.data.authors[authorid].twitter %}
          <li>
            <a href="https://twitter.com/{{ site.data.authors[authorid].twitter }}" itemprop="sameAs">
              <i class="fa fa-fw fa-twitter-square" aria-hidden="true"></i> Twitter
            </a>
          </li>
        {% endif %}

        {% if site.data.authors[authorid].facebook %}
          <li>
            <a href="https://www.facebook.com/{{ site.data.authors[authorid].facebook }}" itemprop="sameAs">
              <i class="fa fa-fw fa-facebook-square" aria-hidden="true"></i> Facebook
            </a>
          </li>
        {% endif %}

        {% if site.data.authors[authorid].google_plus %}
          <li>
            <a href="https://plus.google.com/{{ site.data.authors[authorid].google_plus }}" itemprop="sameAs">
              <i class="fa fa-fw fa-google-plus-square" aria-hidden="true"></i> Google+
            </a>
          </li>
        {% endif %}

        {% if site.data.authors[authorid].linkedin %}
          <li>
            <a href="https://www.linkedin.com/in/{{ site.data.authors[authorid].linkedin }}" itemprop="sameAs">
              <i class="fa fa-fw fa-linkedin-square" aria-hidden="true"></i> LinkedIn
            </a>
          </li>
        {% endif %}

        {% if site.data.authors[authorid].xing %}
          <li>
            <a href="https://www.xing.com/profile/{{ site.data.authors[authorid].xing }}" itemprop="sameAs">
              <i class="fa fa-fw fa-xing-square" aria-hidden="true"></i> XING
            </a>
          </li>
        {% endif %}

        {% if site.data.authors[authorid].instagram %}
          <li>
            <a href="https://instagram.com/{{ site.data.authors[authorid].instagram }}" itemprop="sameAs">
              <i class="fa fa-fw fa-instagram" aria-hidden="true"></i> Instagram
            </a>
          </li>
        {% endif %}

        {% if site.data.authors[authorid].tumblr %}
          <li>
            <a href="https://{{ site.data.authors[authorid].tumblr }}.tumblr.com" itemprop="sameAs">
              <i class="fa fa-fw fa-tumblr-square" aria-hidden="true"></i> Tumblr
            </a>
          </li>
        {% endif %}

        {% if site.data.authors[authorid].bitbucket %}
          <li>
            <a href="https://bitbucket.org/{{ site.data.authors[authorid].bitbucket }}" itemprop="sameAs">
              <i class="fa fa-fw fa-bitbucket" aria-hidden="true"></i> Bitbucket
            </a>
          </li>
        {% endif %}

        {% if site.data.authors[authorid].github %}
          <li>
            <a href="https://github.com/{{ site.data.authors[authorid].github }}" itemprop="sameAs">
              <i class="fa fa-fw fa-github" aria-hidden="true"></i> GitHub
            </a>
          </li>
        {% endif %}

        {% if site.data.authors[authorid].gitlab %}
          <li>
            <a href="https://gitlab.com/{{ site.data.authors[authorid].gitlab }}" itemprop="sameAs">
              <i class="fa fa-fw fa-gitlab" aria-hidden="true"></i> GitLab
            </a>
          </li>
        {% endif %}

        {% if site.data.authors[authorid].stackoverflow %}
          <li>
            <a href="https://www.stackoverflow.com/users/{{ site.data.authors[authorid].stackoverflow }}" itemprop="sameAs">
              <i class="fa fa-fw fa-stack-overflow" aria-hidden="true"></i> Stack Overflow
            </a>
          </li>
        {% endif %}

        {% if site.data.authors[authorid].lastfm %}
          <li>
            <a href="https://last.fm/user/{{ site.data.authors[authorid].lastfm }}" itemprop="sameAs">
              <i class="fa fa-fw fa-lastfm-square" aria-hidden="true"></i> Last.fm
            </a>
          </li>
        {% endif %}

        {% if site.data.authors[authorid].dribbble %}
          <li>
            <a href="https://dribbble.com/{{ site.data.authors[authorid].dribbble }}" itemprop="sameAs">
              <i class="fa fa-fw fa-dribbble" aria-hidden="true"></i> Dribbble
            </a>
          </li>
        {% endif %}

        {% if site.data.authors[authorid].pinterest %}
          <li>
            <a href="https://www.pinterest.com/{{ site.data.authors[authorid].pinterest }}" itemprop="sameAs">
              <i class="fa fa-fw fa-pinterest" aria-hidden="true"></i> Pinterest
            </a>
          </li>
        {% endif %}

        {% if site.data.authors[authorid].foursquare %}
          <li>
            <a href="https://foursquare.com/{{ site.data.authors[authorid].foursquare }}" itemprop="sameAs">
              <i class="fa fa-fw fa-foursquare" aria-hidden="true"></i> Foursquare
            </a>
          </li>
        {% endif %}

        {% if site.data.authors[authorid].steam %}
          <li>
            <a href="https://steamcommunity.com/id/{{ site.data.authors[authorid].steam }}" itemprop="sameAs">
              <i class="fa fa-fw fa-steam-square" aria-hidden="true"></i> Steam
            </a>
          </li>
        {% endif %}

        {% if site.data.authors[authorid].youtube %}
          {% if site.data.authors[authorid].youtube contains "://" %}
            <li>
              <a href="{{ site.data.authors[authorid].youtube }}" itemprop="sameAs">
                <i class="fa fa-fw fa-youtube-square" aria-hidden="true"></i> YouTube
              </a>
            </li>
          {% else site.data.authors[authorid].youtube %}
            <li>
              <a href="https://www.youtube.com/user/{{ site.data.authors[authorid].youtube }}" itemprop="sameAs">
                <i class="fa fa-fw fa-youtube-square" aria-hidden="true"></i> YouTube
              </a>
            </li>
          {% endif %}
        {% endif %}

        {% if site.data.authors[authorid].soundcloud %}
          <li>
            <a href="https://soundcloud.com/{{ site.data.authors[authorid].soundcloud }}" itemprop="sameAs">
              <i class="fa fa-fw fa-soundcloud" aria-hidden="true"></i> SoundCloud
            </a>
          </li>
        {% endif %}

        {% if site.data.authors[authorid].weibo %}
          <li>
            <a href="https://www.weibo.com/{{ site.data.authors[authorid].weibo }}" itemprop="sameAs">
              <i class="fa fa-fw fa-weibo" aria-hidden="true"></i> Weibo
            </a>
          </li>
        {% endif %}

        {% if site.data.authors[authorid].flickr %}
          <li>
            <a href="https://www.flickr.com/{{ site.data.authors[authorid].flickr }}" itemprop="sameAs">
              <i class="fa fa-fw fa-flickr" aria-hidden="true"></i> Flickr
            </a>
          </li>
        {% endif %}

        {% if site.data.authors[authorid].codepen %}
          <li>
            <a href="https://codepen.io/{{ site.data.authors[authorid].codepen }}" itemprop="sameAs">
              <i class="fa fa-fw fa-codepen" aria-hidden="true"></i> CodePen
            </a>
          </li>
        {% endif %}

        {% if site.data.authors[authorid].vine %}
          <li>
            <a href="https://vine.co/u/{{ site.data.authors[authorid].vine }}" itemprop="sameAs">
              <i class="fa fa-fw fa-vine" aria-hidden="true"></i> Vine
            </a>
          </li>
        {% endif %}

        {% include author-profile-custom-links.html %}
      </ul>
    </div>
  </p>
  {% endfor %}
</div>

<div class="page__inner-wrap">
# People

<img src="https://uploads-ssl.webflow.com/58920a954e6c16dd742902c4/58bf991c33a88a2f69b0bc6c_chris-p-500x500.jpeg" width="250">

### Christoph Riedl
Chris is Assistant Professor for Information Systems at the D’Amore McKim School of Business. He employs business analytics and data science to investigate research questions about group-decision making, network science, and social media, and develops novel computational approaches to study collective intelligence mechanisms.

## Post-docs and Students


<img src="https://uploads-ssl.webflow.com/58920a954e6c16dd742902c4/58920a954e6c16dd7429057d_stefano_mini%20(2).jpg" width="250"> 

### Stefano Balietti

#### postdoctoral research associate

[****stefanobalietti.com](http://stefanobalietti.com/)

Stefano Balietti is a Postdoctoral Researcher at the Network Science Institute, and a Fellow at the Harvard Institute for Quantitative Social Sciences (IQSS). His research interests involve: incentives schemes for peer review systems, consensus formation and social influence -- in particular in epistemic communities, equality and efficiency in public-goods games, efficiency in coordination games, philosophy of science -- in particular Paul Feyerabend's body of work. His methodology aims at bringing together agent-based computer simulations and behavioral experiments. He is also an active developer, and he created a JavaScript platform for conducting real-time online behavioral experiments directly in the browser called  [nodeGame](http://www.nodegame.org/).





<img src="https://uploads-ssl.webflow.com/58920a954e6c16dd742902c4/58920a954e6c16dd74290517_sam_picture%20(1).jpg" width="250">

### Sam Fraiberger

#### postdoctoral research associate

[****samuelfraiberger.com](http://samuelfraiberger.com/)

[****LinkedIn](mailto:https://www.linkedin.com/in/samuelfraiberger)

Sam Fraiberger is a currently a Postdoctoral Research Associate at the Network Science Institute, a Fellow at the Harvard Institute for Quantitative Social Sciences (IQSS) and a Visiting Scholar at the Department of Information, Operations & Management Sciences (IOMS) at the NYU Stern School of Business. He received his BS in Applied Mathematics from Ecole Centrale Paris, his SM in Applied Mathematics from Harvard University and his PhD in Economics from New York University. His research program is at the interface of Behavioral Economics, Data Science and Computational Social Sciences, and focuses on using large datasets and experimental methods to answer questions of economic and social significance. His research has been featured in the Washington Post, Fast Company and Mashable.

<img src="https://uploads-ssl.webflow.com/58920a954e6c16dd742902c4/58920a954e6c16dd74290490_mike.jpg" width="250">

### Michael Foley

#### third year phd student

[****Michael](mailto:tina@eliassi.org)

Michael's broad research interests lie in the overlap between complex systems and the social sciences. In particular, he is interested in how rational local decisions and interactions can produce unintended and emergent system behavior. Michael has a B.S. and M.S. in Mathematics from the University of Vermont, where he did research in computational finance and agent based modeling. Currently, he is working with Chris Riedl to research the effect of different communication networks on a group's ability to solve problems.

<img src="https://uploads-ssl.webflow.com/58920a954e6c16dd742902c4/58920a954e6c16dd742903e4_brennan2016_original.jpeg" width="250">

### Brennan Klein

#### second year phd student

[****Brennan](mailto:klein.br@husky.neu.edu)

[****@jkbren](https://twitter.com/jkbren)

Brennan received his BA in Cognitive Science and Psychology from Swarthmore College in 2014. While attending Swarthmore, Brennan’s research revolved primarily around perception and cognition. He has presented at Vision Science Society’s Annual Conference (2012, 2013, 2014) is a co-author on several cognitive science papers. Before starting his PhD, Brennan spent a year in Silicon Valley trying to start a startup while working as a social network data analyst (June 2014 - May 2015).

<img src="https://uploads-ssl.webflow.com/58920a954e6c16dd742902c4/58920a954e6c16dd7429039f_Photo-Praveen.png" width="250">

### Praveen Ningappa

#### masters student

Praveen received his undergraduate degree from India in the field of Electronics & Communication. Currently he is pursuing a  
master’s degree at Northeastern University in Information Systems. His area of specialization is Front End Design and Development. Praveen's research interest is in developing an User Interface which provides a better user experience even for visually challenged users.

<img src="https://uploads-ssl.webflow.com/58920a954e6c16dd742902c4/58920a954e6c16dd7429055d_jake.jpeg" width="250">

### Jake Moody

#### undergraduate student

Jake is an undergraduate student at the D'Amore-McKim School of Business concentrating in Finance and Entrepreneurship. His research interests are in business analytics and digital marketing.

<img src="https://uploads-ssl.webflow.com/58920a954e6c16dd742902c4/58920a954e6c16dd742904d7_website-christina-sirabella.jpg" width="250">

### Christina Sirabella

#### undergraduate student

Christina is an undergraduate student in the College of Arts, Media, and Design studying Communications with minors in Women's Studies and Sociology. She is interested in exploring the social and cultural impact of digital networks and technologies.

<img src="https://uploads-ssl.webflow.com/58920a954e6c16dd742902c4/58920a954e6c16dd742903a3_website-tina-lee.jpg" width="250">

### Tina Lee

#### undergraduate student

Tina is an undergraduate student at the College of Computer and Information Science majoring in computer science. Her research interests are in human-computer interaction and artificial intelligence.
</div>