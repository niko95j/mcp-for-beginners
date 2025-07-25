<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "b1cffc51b82049ac3d5e88db0ff4a0a1",
  "translation_date": "2025-06-12T21:32:31+00:00",
  "source_file": "05-AdvancedTopics/README.md",
  "language_code": "fr"
}
-->
# Sujets avancés en MCP

Ce chapitre couvre une série de sujets avancés dans l’implémentation du Model Context Protocol (MCP), incluant l’intégration multimodale, la scalabilité, les bonnes pratiques de sécurité et l’intégration en entreprise. Ces thèmes sont essentiels pour construire des applications MCP robustes et prêtes pour la production, capables de répondre aux exigences des systèmes d’IA modernes.

## Aperçu

Cette leçon explore des concepts avancés dans l’implémentation du Model Context Protocol, en mettant l’accent sur l’intégration multimodale, la scalabilité, les meilleures pratiques de sécurité et l’intégration en entreprise. Ces sujets sont indispensables pour développer des applications MCP de qualité professionnelle capables de gérer des besoins complexes dans des environnements d’entreprise.

## Objectifs d’apprentissage

À la fin de cette leçon, vous serez capable de :

- Implémenter des fonctionnalités multimodales au sein des frameworks MCP
- Concevoir des architectures MCP évolutives pour des scénarios à forte demande
- Appliquer les meilleures pratiques de sécurité conformes aux principes de sécurité de MCP
- Intégrer MCP avec les systèmes et frameworks d’IA en entreprise
- Optimiser les performances et la fiabilité en environnement de production

## Leçons et projets d’exemple

| Lien | Titre | Description |
|------|-------|-------------|
| [5.1 Integration with Azure](./mcp-integration/README.md) | Intégration avec Azure | Apprenez à intégrer votre serveur MCP sur Azure |
| [5.2 Multi modal sample](./mcp-multi-modality/README.md) | Exemples multimodaux MCP | Exemples pour réponses audio, image et multimodales |
| [5.3 MCP OAuth2 sample](../../../05-AdvancedTopics/mcp-oauth2-demo) | Démo MCP OAuth2 | Application Spring Boot minimaliste montrant OAuth2 avec MCP, à la fois comme serveur d’autorisation et serveur de ressources. Démonstration de l’émission sécurisée de jetons, des points de terminaison protégés, du déploiement sur Azure Container Apps et de l’intégration avec API Management. |
| [5.4 Root Contexts](./mcp-root-contexts/README.md) | Contextes racines | En savoir plus sur les contextes racines et leur implémentation |
| [5.5 Routing](./mcp-routing/README.md) | Routage | Apprenez les différents types de routage |
| [5.6 Sampling](./mcp-sampling/README.md) | Échantillonnage | Apprenez à travailler avec l’échantillonnage |
| [5.7 Scaling](./mcp-scaling/README.md) | Scalabilité | Découvrez la scalabilité |
| [5.8 Security](./mcp-security/README.md) | Sécurité | Sécurisez votre serveur MCP |
| [5.9 Web Search sample](./web-search-mcp/README.md) | Recherche web MCP | Serveur et client MCP Python intégrant SerpAPI pour la recherche web, d’actualités, de produits et Q&A en temps réel. Montre l’orchestration multi-outils, l’intégration d’API externes et une gestion robuste des erreurs. |
| [5.10 Realtime Streaming](./mcp-realtimestreaming/README.md) | Streaming | Le streaming de données en temps réel est devenu essentiel dans un monde axé sur les données, où entreprises et applications nécessitent un accès immédiat à l’information pour prendre des décisions rapides. |
| [5.11 Realtime Web Search](./mcp-realtimesearch/README.md) | Recherche web | Comment MCP transforme la recherche web en temps réel en fournissant une approche standardisée de la gestion de contexte entre modèles d’IA, moteurs de recherche et applications. |

## Références supplémentaires

Pour les informations les plus récentes sur les sujets avancés de MCP, consultez :
- [MCP Documentation](https://modelcontextprotocol.io/)
- [MCP Specification](https://spec.modelcontextprotocol.io/)
- [GitHub Repository](https://github.com/modelcontextprotocol)

## Points clés à retenir

- Les implémentations MCP multimodales étendent les capacités d’IA au-delà du traitement textuel
- La scalabilité est cruciale pour les déploiements en entreprise et peut être abordée par une montée en charge horizontale et verticale
- Des mesures de sécurité complètes protègent les données et garantissent un contrôle d’accès approprié
- L’intégration en entreprise avec des plateformes comme Azure OpenAI et Microsoft AI Foundry renforce les capacités de MCP
- Les implémentations avancées de MCP tirent profit d’architectures optimisées et d’une gestion rigoureuse des ressources

## Exercice

Concevez une implémentation MCP de niveau entreprise pour un cas d’usage spécifique :

1. Identifiez les besoins multimodaux pour votre cas d’usage
2. Décrivez les contrôles de sécurité nécessaires pour protéger les données sensibles
3. Concevez une architecture évolutive capable de gérer des charges variables
4. Planifiez les points d’intégration avec les systèmes d’IA d’entreprise
5. Documentez les éventuels goulets d’étranglement en termes de performance et les stratégies d’atténuation

## Ressources supplémentaires

- [Documentation Azure OpenAI](https://learn.microsoft.com/en-us/azure/ai-services/openai/)
- [Documentation Microsoft AI Foundry](https://learn.microsoft.com/en-us/ai-services/)

---

## Prochaines étapes

- [5.1 MCP Integration](./mcp-integration/README.md)

**Avertissement** :  
Ce document a été traduit à l'aide du service de traduction automatique [Co-op Translator](https://github.com/Azure/co-op-translator). Bien que nous nous efforcions d'assurer l'exactitude, veuillez noter que les traductions automatiques peuvent contenir des erreurs ou des inexactitudes. Le document original dans sa langue native doit être considéré comme la source faisant foi. Pour les informations critiques, une traduction professionnelle humaine est recommandée. Nous ne sommes pas responsables des malentendus ou des mauvaises interprétations résultant de l'utilisation de cette traduction.