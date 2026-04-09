# Reviews Fetching Output
date, title, review, rating, language, country, answered (true/false)


## Sur Trustpilot

Pas d'API officielle publique — il faudra scraper. beautifulsoup4 + requests peut marcher mais Trustpilot est agressif sur le scraping. Complexité: 45/100 — faisable mais plus fragile que les deux autres sources. À tester en priorité avant de l'intégrer dans l'archi.

## Output structuré:
Pense dès maintenant au format JSON de sortie de Claude — ça facilitera énormément le passage au micro SaaS ensuite. Quelque chose comme:
json{
  "period": "30d",
  "problems": [...],
  "neutral": [...],
  "strengths": [...],
  "trend": "+0.2 vs previous period"
}
Sur l'archi globale:
Sépare bien scraping et analyse en deux notebooks ou deux modules distincts dès maintenant — ça sera beaucoup plus propre quand tu passeras à l'UI.


