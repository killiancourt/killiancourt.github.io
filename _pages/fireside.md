---
layout: page
title: fireside chats
permalink: /fireside/
description: Conversations Beyond the Firewall
nav: true
nav_order: 2
---

<style>
  .fireside-intro {
    font-size: 1.05rem;
    line-height: 1.8;
    margin-bottom: 2rem;
  }

  .fireside-entry {
    padding: 2rem 0;
    border-bottom: 1px solid var(--global-divider-color);
  }

  .fireside-portrait {
    width: 100%;
    aspect-ratio: 3 / 4;
    object-fit: cover;
    border-radius: 6px;
  }

  .fireside-meta {
    font-size: 0.75rem;
    letter-spacing: 1.2px;
    text-transform: uppercase;
    color: var(--global-text-color-light);
    margin-bottom: 0.6rem;
  }

  .fireside-title {
    font-size: 1.55rem;
    font-weight: 600;
    line-height: 1.3;
    margin-bottom: 0.8rem;
  }

  .fireside-guest {
    font-size: 1.05rem;
    font-weight: 600;
    margin-bottom: 0.2rem;
  }

  .fireside-affiliation {
    font-size: 0.9rem;
    color: var(--global-text-color-light);
    margin-bottom: 1rem;
  }

  .fireside-summary {
    font-size: 0.95rem;
    line-height: 1.7;
  }

  .fireside-tag {
    display: inline-block;
    border: 1px solid var(--global-divider-color);
    border-radius: 4px;
    padding: 3px 9px;
    margin: 0 4px 5px 0;
    font-size: 0.75rem;
  }

  .fireside-links {
    margin-top: 1rem;
    font-size: 0.9rem;
  }

  .fireside-links a {
    margin-right: 1.2rem;
  }

  .fireside-filter {
    cursor: pointer;
    border: 1px solid var(--global-divider-color);
    background: transparent;
    color: var(--global-text-color);
    padding: 6px 14px;
    border-radius: 4px;
    margin: 0 5px 8px 0;
    font-size: 0.85rem;
  }

  .fireside-filter.active {
    background: var(--global-theme-color);
    border-color: var(--global-theme-color);
    color: white;
  }

  @media (max-width: 767px) {
    .fireside-portrait {
      max-width: 180px;
      margin-bottom: 1rem;
    }

    .fireside-title {
      font-size: 1.3rem;
    }
  }
</style>

<div class="fireside-intro">
  <p>
    An ongoing series of conversations with researchers,
    industry practitioners, and policymakers exploring
    the people, ideas, and technologies shaping the
    future of cybersecurity.
  </p>

  <p>
    From cryptography and artificial intelligence to
    digital trust and national security, Fireside Chats
    seeks to bridge technical knowledge with broader
    questions about technology and society.
  </p>
</div>

<!-- Category filters -->

<div class="mb-3">

  <button class="fireside-filter active"
          onclick="filterFireside('all', this)">
    All Conversations
  </button>

  <button class="fireside-filter"
          onclick="filterFireside('research', this)">
    Academic Research
  </button>

  <button class="fireside-filter"
          onclick="filterFireside('industry', this)">
    Industry
  </button>

  <button class="fireside-filter"
          onclick="filterFireside('policy', this)">
    Public Policy
  </button>

</div>

<hr>

<!-- Automatically generate interview entries -->

{% assign interviews = site.fireside | sort: "date" | reverse %}

{% for interview in interviews %}

<div class="fireside-entry"
     data-category="{{ interview.category }}">

  <div class="row">

    <!-- Guest portrait -->

    <div class="col-md-3 col-sm-4">

      <a href="{{ interview.url | relative_url }}">

        <img
          src="{{ interview.image | relative_url }}"
          alt="Portrait of {{ interview.guest | escape }}"
          class="fireside-portrait"
          loading="lazy">

      </a>

    </div>

    <!-- Interview information -->

    <div class="col-md-9 col-sm-8">

      <div class="fireside-meta">
        Episode {{ interview.episode }}
        &nbsp;·&nbsp;
        {{ interview.date | date: "%B %Y" }}
        &nbsp;·&nbsp;
        {{ interview.category_label }}
      </div>

      <h2 class="fireside-title">

        <a href="{{ interview.url | relative_url }}">
          {{ interview.title }}
        </a>

      </h2>

      <div class="fireside-guest">
        {{ interview.guest }}
      </div>

      <div class="fireside-affiliation">
        {{ interview.position }}
        <br>
        {{ interview.organization }}
      </div>

      <p class="fireside-summary">
        {{ interview.summary }}
      </p>

      <!-- Topic tags -->

      <div>

        {% for tag in interview.tags %}

          <span class="fireside-tag">
            {{ tag }}
          </span>

        {% endfor %}

      </div>

      <!-- Episode links -->

      <div class="fireside-links">

        <a href="{{ interview.url | relative_url }}">
          Explore Conversation &rarr;
        </a>

        {% if interview.youtube_id %}

          <a
            href="https://www.youtube.com/watch?v={{ interview.youtube_id }}"
            target="_blank"
            rel="noopener noreferrer">

            <i class="fab fa-youtube"></i>
            Watch on YouTube

          </a>

        {% endif %}

      </div>

    </div>

  </div>

</div>

{% endfor %}

{% if interviews.size == 0 %}

<p class="text-muted">
  Our first conversation is coming soon.
</p>

{% endif %}

<p class="text-center text-muted mt-5">
  Exploring cybersecurity, one conversation at a time.
</p>

<script>
  function filterFireside(category, button) {

    document.querySelectorAll('.fireside-entry')
      .forEach(function(entry) {

        entry.style.display =
          category === 'all' ||
          entry.dataset.category === category
            ? ''
            : 'none';

      });

    document.querySelectorAll('.fireside-filter')
      .forEach(function(item) {
        item.classList.remove('active');
      });

    button.classList.add('active');
  }
</script>
