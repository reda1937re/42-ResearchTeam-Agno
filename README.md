# ResearchTeam-Agno

Équipe multi-agents (Agno `Team`, mode `coordinate`) pour la recherche web. Un **Chercheur** dispose de l'outil `firecrawl_search` et décide lui-même quand/combien de fois l'appeler (agent "agentique", contrairement aux agents Firecrawl mono-outil des projets 37-40). Un **Rédacteur** vérifie la cohérence des sources et rédige le rapport final. Le leader de l'équipe orchestre la délégation entre les deux.

## Fonctionnement

1. `firecrawl_search()` — outil donné au Chercheur, pas appelé directement par le code
2. `run_research()` — lance l'équipe, avec un filet de sécurité qui détecte les échecs silencieux (erreur API renvoyée comme si c'était une réponse valide)

## Tech stack

- **Streamlit** — interface web (visualisation du pipeline chercheur → rédacteur)
- **Agno** — `Team` en mode `coordinate`
- **Firecrawl** — recherche web (outil de l'agent)
- **Groq** (`openai/gpt-oss-20b`, quota plus élevé que 120b) — LLM des 2 agents + du leader

## Lancer le projet

```bash
pip install -r requirements.txt
```

Créer un fichier `.env` avec :
```
GROQ_API_KEY=...
FIRECRAWL_API_KEY=...
```

```bash
streamlit run app.py
```
