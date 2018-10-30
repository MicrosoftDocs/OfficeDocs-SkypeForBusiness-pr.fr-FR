---
title: Composants utilisés par la prise d’appel de groupe
TOCTitle: Composants utilisés par la prise d’appel de groupe
ms:assetid: 45db2f23-d486-4b20-a8cf-7b48a1f9fd3a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ945625(v=OCS.15)
ms:contentKeyID: 53095404
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Composants utilisés par la prise d’appel de groupe

 

_**Dernière rubrique modifiée :** 2013-01-30_

La prise d’appel de groupe est automatiquement déployée quand vous déployez Voix Entreprise et l’application de parcage d’appel. Vous activez la prise d’appel de groupe en configurant la plage des numéros de parcage d’appel avec des plages de numéros distincts définies en tant que numéros de groupe de prise d’appel, puis en affectant des utilisateurs aux groupes de prise d’appel et en activant les utilisateurs pour la prise d’appel de groupe. Les composants Lync Server suivants prennent en charge la prise d’appel de groupe :

  - **service d’application**   Le service d’application fournit une plateforme pour le déploiement, l’hébergement et la gestion des applications de communications unifiées, telles que l’application de parcage d’appel. Le service d’application est installé automatiquement sur chaque serveur frontal dans un pool de serveurs frontaux et sur chaque serveur Standard Edition.

  - **application de parcage d’appel**   L’application de parcage d’appel est l’une des applications de communications unifiées hébergées par le service d’application. La prise d’appel de groupe repose sur l’application de parcage d’appel.

  - **Lync Server Management Shell**   Lync Server Management Shell vous permet de gérer les groupes de prise d’appel de groupe.

  - **Outil de kit de ressources SEFAUtil**   L’utilitaire SEFAUtil (Secondary Extension Feature Activation Utility) vous permet d’affecter des utilisateurs à un groupe de prise d’appel et d’activer ou de désactiver la prise d’appel pour les utilisateurs.

