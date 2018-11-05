---
title: Migration des réunions et des contenus de réunion existants
TOCTitle: Migration des réunions et des contenus de réunion existants
ms:assetid: 30516731-2ae1-4a6d-a7e1-d3f05778c954
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688011(v=OCS.15)
ms:contentKeyID: 49891289
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migration des réunions et des contenus de réunion existants

 

_**Dernière rubrique modifiée :** 2013-02-22_

Lorsque vous déplacez un compte d’utilisateur de Lync Server 2010 vers un serveur Lync Server 2013, les informations suivantes se déplacent avec le compte d’utilisateur :

  - **Réunions déjà planifiées par l’utilisateur** : cela comprend le déplacement des répertoires de conférence et des données de conférence.

  - **Code confidentiel de l’utilisateur** : le code confidentiel actuel de l’utilisateur fonctionne jusqu’à ce qu’il expire ou que l’utilisateur en demande un nouveau.

Les informations de compte d’utilisateur suivantes ne se déplacent pas vers le nouveau serveur.

  - **Contenu de la réunion** : pour déplacer le contenu partagé pendant une réunion, par exemple, PowerPoint, Tableau blanc, pièces jointes ou données d’interrogation, utilisez le paramètre **-MoveConferenceData** dans le cadre de l’applet de commande **Move-CsUser**.

