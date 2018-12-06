---
title: Configurer les extensions de numéro de téléphone pour le parcage d’appel
TOCTitle: Configurer les extensions de numéro de téléphone pour le parcage d’appel
ms:assetid: fbf97624-9587-42a6-b276-1b69c574a74d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg182611(v=OCS.15)
ms:contentKeyID: 49299448
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurer les extensions de numéro de téléphone pour le parcage d’appel

 

_**Dernière rubrique modifiée :** 2012-09-10_

L’application de parcage d’appel utilise des numéros d’extension dans la table d’orbite du parcage d’appelpour parquer les appels. Vous devez configurer la table d’orbite du parcage d’appel avec les plages de numéros de poste que votre organisation réserve pour les appels parqués. Ces extensions doivent être des postes virtuels (c’est à dire, des postes auxquels aucun utilisateur ou téléphone n’a été affecté). Chaque pool Lync Server où une application de parcage d’appel est déployée et configurée peut avoir une ou plusieurs plages d’orbite. Les plages d’orbites doivent être globalement uniques sur le déploiement Lync Server.

> [!IMPORTANT]  
> Vous devez sélectionner la case à cocher <strong>Activer le parcage d’appel</strong> dans votre stratégie de la voix avant de pouvoir utiliser le parcage d’appel. Par défaut, cette option n’est pas sélectionnée.

## Dans cette section

  - [Création ou modification d’une plage d’orbites de parcage d’appel dans Lync Server 2013](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

  - [Supprimer une plage d’orbites de parcage d’appel dans Lync Server 2013](lync-server-2013-delete-a-call-park-orbit-range.md)

