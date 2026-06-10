# MSPR 3 : Livrables TPRE601

**Mise en production de la plateforme HealthAI Coach**

Formation : Concepteur Developpeur d'Applications, Blocs E6.3 et E6.4
Annee : 2025-2026
Ecole : EPSI

## Equipe projet

Arthur Poncin, Theo Renard, Martin Ornh, Foidjou Daumard

## Perimetre

Industrialisation et mise en production de la plateforme microservices HealthAI Coach
construite lors des MSPR1 (backend metier) et MSPR2 (IA et frontend) : conteneurisation,
orchestration locale (Docker Compose), observabilite, CI/CD, securite, configurations
multi-environnement et resilience.

L'application mobile (mini reseau social) est developpee par un autre membre de l'equipe :
elle ne fait pas partie de ce dossier de livrables.

## Arborescence des livrables

| Dossier | Livrable |
|---------|----------|
| `01-conteneurisation-orchestration/` | Architecture de deploiement, fichiers Docker Compose (base + overlays : monitoring, offline, performance, traefik, vision, watchtower), `bootstrap.sh`, scripts de sauvegarde/restauration, `CONFIGS.pdf` |
| `02-observabilite-supervision/` | Procedure de supervision, documentation technique du monitoring (Prometheus, Grafana, Loki, Alertmanager) et captures des tableaux de bord en fonctionnement |
| `03-ci-cd-qualite/` | Chaine CI/CD (GitHub Actions, GHCR, deploiement continu Watchtower), plan de test, rapport de tests et indicateurs de qualite (couvertures, SonarCloud) avec captures |
| `04-securite/` | Analyse de securite : OWASP Top 10, RGPD, NIST CSF |
| `05-gestion-de-projet/` | Demarche agile, decoupage en 4 sprints, Kanban (capture du GitHub Project commun), gestion des risques |

## Source du projet

Le code et l'orchestration sont repartis sur des depots independants :

- Orchestration et mise en production : depot `MSPR-Deploy` (point d'entree `bootstrap.sh`,
  source canonique des documents de ce dossier).
- 8 services applicatifs : depots `whitefoxxyt/MSPR-HealthAI-Coach-*` (images publiees sur
  `ghcr.io/whitefoxxyt/mspr-<service>`).
- Livrables des MSPR precedentes : `MSPR-TPRE501-HealthAI-Coach` (MSPR1) et
  `MSPR-TPRE502-HealthAI-Coach` (MSPR2).

## Note de format

Les documents sont fournis en PDF, generes depuis les sources Markdown du depot
`MSPR-Deploy` (diagrammes Mermaid rendus). Les fichiers de
configuration (`docker-compose*.yml`, `bootstrap.sh`, scripts) sont des copies fideles de
ceux du depot `MSPR-Deploy`.
