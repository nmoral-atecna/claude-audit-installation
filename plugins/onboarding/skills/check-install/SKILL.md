---
name: check-install
description: Audite la procédure d'installation du projet courant comme un nouveau développeur, depuis un clone vierge et isolé, puis rend un rapport (bloquants, trous de documentation, portabilité macOS/Ubuntu).
argument-hint: "[ref git à auditer, par défaut le commit courant]"
disable-model-invocation: true
---

Lance un audit d'installation du projet courant.

1. Délègue l'intégralité de l'audit au subagent `onboarding:audit-installation` (fourni par ce plugin). Ne fais aucune étape de l'audit toi-même : les sorties d'installation sont longues et doivent rester dans le contexte du subagent.
2. Transmets-lui :
   - la racine du dépôt courant ;
   - la ref à auditer : `$ARGUMENTS` si elle est renseignée, sinon le commit courant (`HEAD`).
3. Quand il a terminé, affiche son rapport tel quel, sans le résumer ni le réécrire.
4. Termine par une seule ligne proposant, s'il y a des bloquants ou des trous de documentation, d'en faire une issue ou une MR sur la documentation d'installation. N'agis pas sans réponse.
