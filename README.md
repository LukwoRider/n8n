

Aller au contenu
Utiliser Messagerie NEXT-U Education avec un lecteur d'écran

Conversations
 
Règlement du programme
Fourni par Google
Dernière activité sur le compte : il y a 3 minutes
Détails
# Module Automatisation N8N & IA

## I. Objectif du projet 🎯

Concevoir et développer un assistant personnel intelligent utilisant N8N qui vous aidera à gérer votre quotidien professionnel et/ou personnel. Cet assistant devra être capable de recevoir des demandes en langage naturel et d'effectuer automatiquement diverses actions pour vous avant de vous répondre.

## II. Modalités ⚙️

**Groupe** : Individuel, binôme ou trinôme. [Déclare ton groupe sur ce formulaire](https://tally.so/r/ob9bpb), même si tu es tout(e) seul(e).

**Date butoir de rendu** : Lundi 15 Décembre à 09h00<br>
_(je vous conseille de le rendre bien avant)_

**Format de rendu** : Lien dossier Google Drive via email à <aris+next-u2025@arisfv.me>

L'objet du mail sera **`Rendu N année ESCEN`** (remplacer le **N** par l'année en cours : "3e", "4e" ou "5e")

**Contenu du rendu** : Workflow N8N exporté + Vidéo d'utilisation de toutes les fonctionnalités.<br>
_Le partage d'un export json d'un workflow N8N n'expose pas vos identifiants._

La vidéo devra être une capture d'écran de l'interface N8N du workflow, exécuté depuis le bouton "Execute workflow" depuis le nœud déclencheur (afin de voir l'exécution dérouler en temps réel. Je précise : Il ne faut pas juste activer votre workflow mais exécuter le scénario depuis le nœud déclencheur telegram, whatsapp, discord, slack ou autre service de messagerie).

Dans la vidéo il suffit de tester toutes les fonctionnalités une par une en montrant les logs de chaque module. [Consultez cette vidéo d'instructions](https://youtu.be/ZFU4FIBpfJw) pour vous aider à enregistrer votre rendu.

_Vous pouvez utiliser OBS gratuitement pour enregistrer votre écran_

_Pensez bien à partager le dossier Google Drive avec mon email : aris@arisfv.me._

**Sous-workflows** : Pour des raisons de simplicité (afin d'éviter de rendre plusieurs workflows ou devoir jongler entre plusieurs workflows pour enregistrer votre vidéo de rendu) je vous demande de tout faire dans un même workflow.

Même si ce n'est pas une bonne pratique, ça aura le mérite de vous forcer à être organisé et propre face à une grande quantité de nœuds.

Cela ne vous empêche pas d'utiliser des sous-agents.

---

## III. Fonctionnalités attendues 🤖

### A. Déclencheur

Votre assistant doit pouvoir recevoir des requêtes :

- **Entrée textuelle** : Via l'application de votre choix (Telegram, slack, Whatsapp... Attention Whatsapp est plus compliqué à implémenter)
- **Entrée vocale en bonus**

Si vous hébergez votre instance N8N sur un serveur local, vous aurez du mal à recevoir les requêtes d'un webhook. Dans ce cas vous avez deux solutions : configurer votre réseau pour laisser passer un webhook spécifique ou faire du polling. Vous êtes libre de votre choix et ne serez pas notés sur la partie admin réseau ou admin sys de votre instance N8N.

Le système doit ensuite envoyer la demande à un agent IA qui devra utiliser le bon outil en fonction de l'intention détectée.

### B. Agent IA

Vous êtes libres de donner le ton et style de rédaction que vous souhaitez à votre IA.

Pour les outils de votre agent, vous pouvez utiliser les services de votre choix. Google est recommandé pour regrouper certains services dans un seul endroit et ainsi gagner du temps.

Vous pouvez aussi bien utiliser vos données que des fausses données en créant des nouveaux comptes avec 1 faux email, 1 faux événement calendrier, etc...

Voici les outils à donner à votre agent IA :

#### 1. Gestion des emails

- **Récupération** : Récupérer un/plusieurs emails
- **Rédaction** : Créer un brouillon d'email

_Exemple de requête : "Rédige un email pour remercier mon client pour sa commande"_<br>
_Outil conseillé : Gmail_

#### 2. Gestion du calendrier

- **Récupération** : Récupérer un/plusieurs événements
- **Création** : Ajouter un événement au calendrier
- **Mise à jour (bonus)** : Modifier un événement existant

_Exemple de requête : "Ajoute une réunion avec l'équipe marketing demain à 14h"_<br>
_Outil conseillé : Google Calendar_

#### 3. Gestion des tâches

- **Création** : Ajouter une nouvelle tâche
- **Complétion** : Marquer une tâche comme complétée

_Exemple de requête : "Ajoute la tâche acheter de la crème fraîche pour ce soir 18h"_<br>
_Outil conseillé : Google Tasks_

#### 4. Gestion des notes (Notion)

- **Création** : Créer une nouvelle note dans Notion
- Structurer le contenu de manière appropriée

_Exemple de requête : "Crée une note dans ma base d'idées pour ma prochaine video Youtube : Un tutoriel N8N pour construire un agent personnel"_<br>
_Outil conseillé : Notion_<br>
_Outil déconseillé : Google Keep_

#### 5. Veille technologique

Implémenter un système de veille qui :

- Est déclenché en demandant à votre agent une veille technique
- Récupère des articles/actualités sur des sujets de votre choix (par exemple à travers une recherche web si votre LLM vous le permet ou flux RSS)
- Vous fait un résumé

_Exemple de requête : "Fais-moi une veille technique"_

#### 6. RAG - Retrieval Augmented Generation

Implémentez un système de mémoire pour votre assistant :

- **Vectorisation** : Stocker des documents/informations de votre choix dans une base de données persistante
- **Récupération** : Rechercher dans la base de connaissances pour enrichir les réponses
- **Suppression (bonus)** : Gérer automatiquement la suppression de documents obsolètes dans la base vectorielle (par exemple lorsque vous voulez revectoriser un document car il a été mis à jour)

_Cela permettra à votre assistant de connaître certaines informations complexes ou utiles comme par exemple des protocoles spécifiques, des études scientifique ou vos propres informations personnelles_<br>
_Outil conseillé : Supabase_

### C. Envoi de message

Les réponses de votre Agent IA devront être envoyées sur le même service de messagerie utilisé en `A.`.

---

## IV. Fonctionnalités bonus 🎁

Ces autres fonctionnalités vous permettront de gagner des points supplémentaires :

- **Réponse vocale (TTS)** : Générer des réponses en format audio
- **Mise à jour calendrier** : Modification d'événements existants
- **Intégration bourse** : Suivre des actifs boursiers ou crypto
- **Système de rappels** : Définir un rappel avec un délai puis envoyer le rappel au moment voulu

## V. Points de vigilance (Malus) ⚠️

Attention aux aspects suivants qui peuvent impacter négativement votre note :

- **Sécurité (liste non exhaustive)** :

  - Absence de validation des entrées utilisateur
  - Exposition de données sensibles publiquement
  - Permissions trop larges sur les services connectés

- **Architecture** :
  - Workflow monolithique difficile à maintenir
  - Absence de gestion d'erreurs
  - Certains nœuds pas renommés
  - Point bonus pour la clarté générale (tous les modules renommés de manière explicite, utilisation des sticky notes, organisation claire...)

---

## VI. Critères d'évaluation 🎓

Ces critères sont à caractère informatif pour vous donner une idée de la répartition des points. Je me réserve le droit de réajuster ces éléments selon le niveau global de la classe.

| Critère                 | Points      | Description                                    |
| ----------------------- | ----------- | ---------------------------------------------- |
| Fonctionnalités de base | 60 pts      | Email, calendar, tâches, notes, veille         |
| Agent IA et triage      | 15 pts      | Qualité de la compréhension et du routing      |
| RAG                     | 15 pts      | Implémentation et pertinence                   |
| Déclencheur & réponse   | 10 pts      | Implémentation et pertinence                   |
| Bonus                   | 5 pts       | Fonctionnalités supplémentaires, documentation |
| Malus                   | -5 pts      | Sécurité, organisation, clarté                 |
| **Total**               | **100 pts** |                                                |

---

## VII. Conseils pratiques 💡

- Testez chaque fonctionnalité au fur et à mesure au lieu d'essayer de "one shot" toute l'architecture
- Utilisez un service de whiteboard pour réfléchir à votre scénario (comme Whimsical)

**LLM** :

- Attention, l'utilisation d'un LLM via son API est un pricing différent de l'utilisation sur l'interface de chat. Concrètement, même si vous avez un abonnement mensuel il faudra acheter des crédits API qui seront consommés à l'utilisation selon le modèle choisi (se référer à la page de pricing des modèles du fournisseur pour en savoir plus)
- Acheter le montant minimal sur l'API de votre LLM préféré comme Claude, ChatGPT ou perplexity sera le plus facile à implémenter. .50€ centimes devrait largement suffire pour ce projet (tout dépend de votre utilisation)
- Si vous ne voulez/pouvez pas payer, Utilisez les offres étudiantes comme le free tier de Gemini, Azure for students, Openrouter, Ollama si vous avez une machine suffisamment puissante... Une multitude d'offres sont disponibles.
- Limitez les appels au LLM au stricte nécessaire et optimisez les tokens.

## VIII. Ressources utiles 🆘

- [Documentation N8N](https://docs.n8n.io)
- [Documentation Supabase](https://supabase.com/docs)
- [Tutoriels N8N](https://www.youtube.com/@n8n-io)
- [Discord du professeur](https://discord.gg/NEfhjrvnQn)
- [Templates N8N](https://n8n.io/workflows/)
- [Déclaration de groupe](https://tally.so/r/ob9bpb)

## IX. Questions / Support ❓

Pour toute question pendant le projet, n'hésitez pas à :

- Sollicitez le professeur pendant les séances
- [Poser vos question sur le Discord du professeur](https://discord.gg/NEfhjrvnQn)
- Consulter la documentation officielle
- Échanger entre vous !
- Appuyez-vous sur votre LLM préféré

**Bon courage et amusez-vous !** 🚀
Consignes_Assistant_Personnel_N8N.md
Affichage de Consignes_Assistant_Personnel_N8N.md en cours...