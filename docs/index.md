---
layout: default
title: AI Native 사례집
permalink: /
nav_exclude: true
---
<script>
  // Check user's language preference
  var savedLang = localStorage.getItem('preferredLanguage');
  var browserLang = navigator.language || navigator.userLanguage;
  var defaultLang = 'ko'; // Default to Korean

  // Determine language: saved preference > browser language > default
  var targetLang = savedLang || (browserLang.startsWith('ko') ? 'ko' : 'en');

  // If no saved preference, use default
  if (!savedLang) {
    targetLang = defaultLang;
  }

  // Redirect to appropriate language version
  var baseUrl = '{{ site.baseurl }}';
  window.location.href = baseUrl + '/' + targetLang + '/';
</script>

<noscript>
  <p>JavaScript가 비활성화되어 있습니다. 언어를 선택하세요:</p>
  <p>JavaScript is disabled. Please choose your language:</p>
  <ul>
    <li><a href="{{ '/ko/' | relative_url }}">한국어</a></li>
    <li><a href="{{ '/en/' | relative_url }}">English</a></li>
  </ul>
</noscript>