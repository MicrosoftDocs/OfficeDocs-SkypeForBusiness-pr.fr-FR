---
title: Problèmes connus et dépannage à propos de l'audioconférence
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 72979911-5319-4de2-a275-4dd9a0f44fe6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Obtenez la liste des problèmes connus lorsque Microsoft est utilisé comme fournisseur de conférences téléphoniques, leur statut et quelques solutions de contournement. '
ms.openlocfilehash: fba5bfff687121c7b1b64c0e51233ccb576497e2
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164518"
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a>Problèmes connus et dépannage à propos de l'audioconférence

 **Cet article est réservé aux utilisateurs de Skype Entreprise qui utilisent Microsoft comme fournisseur de services d’audioconférence. Elles ne s’appliquent pas aux clients qui utilisent un fournisseur de services d’audioconférence (ACP) tiers.**
  
## <a name="troubleshooting-and-known-issues"></a>Dépannage et problèmes connus

L’audioconférence qui utilise Microsoft comme fournisseur de services d’audioconférence présente des problèmes actuels qui font l’objet d’un suivi et font l’objet de recherches et seront potentiellement résolus lorsque la fonctionnalité sera mise à jour dans les prochaines mises à jour de Microsoft 365.
  
Pour l’instant, utilisez cette référence pour résoudre les problèmes potentiels de mise en place et de fonctionnement de l’audioconférence pour les personnes qui utilisent Skype Entreprise dans votre organisation.

|**Problème**|**Comportement/symptômes**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Les notifications d’entrée et de sortie sont désactivées lorsqu’une réunion commence, mais elles sont désactivées peu de temps après le début de la réunion.  <br/> |Par défaut, les notifications d’entrée et de sortie sont désactivées pour les réunions que les participants rejoignent à partir des deux applications Skype Entreprise et lorsqu’ils composent le numéro. Vous pouvez activer les annonces dans les **options de réunion Skype** de l’application Skype Entreprise. Dans le cadre d'une réunion où tous les participants doivent composer le numéro et rejoindre la réunion, les notifications d'entrée et de sortie sont activées par défaut, car les participants n'ont pas tous accès à la liste des participants. Lorsqu’une réunion a commencé et que tous les participants l’ont rejointe en appelant, les notifications d’entrée et de sortie sont désactivées, mais lorsqu’un participant rejoint la réunion à l’aide d’une application Skype Entreprise, les notifications sont désactivées. Lorsque les notifications sont désactivées, vous pouvez les activer de nouveau à l’aide des options de réunion **Skype** dans l’application Skype Entreprise. <br/> |Aucune solution.  <br/> |30/8/2017  <br/> |
|Si un utilisateur reçoit une licence E5 pour la première fois, il est possible que l’e-mail de bienvenue de l’Audioconférence ne soit pas remis à l’utilisateur si la boîte aux lettres n’est pas activée.  <br/> |Dans ce cas, vous pouvez toujours renvoyer les informations d’audioconférence de l’utilisateur à l’aide de l’audioconférence dans le Centre d’administration Skype Entreprise ou à l’aide de PowerShell.  Voir Activer ou désactiver l’envoi de courriers électroniques en cas de modification des [paramètres d’audioconférence.](enable-or-disable-sending-emails-when-their-settings-change.md)  <br/> **Remarque :** Pour renvoyer le code confidentiel de l’audioconférence à l’utilisateur, le code confidentiel doit être réinitialisé. Vous pouvez également utiliser **l’audioconférence** dans le Centre d’administration Skype Entreprise ou PowerShell.          |Aucune solution.  <br/> |30/8/2017  <br/> |
|Les appels d’audioconférence peuvent prendre jusqu’à 24 heures pour s’afficher dans les rapports d’utilisation.  <br/> |Nous espérons apporter des améliorations dans ce domaine dans les prochaines mises à jour de service.  <br/> |Aucune solution.  <br/> |30/8/2017  <br/> |
|Lorsqu’un appelant appelle pour se rendre sur un pont de conférence après que la réunion a été verrouillée par un utilisateur Skype Entreprise, l’application Skype Entreprise ne vous avertit pas que l’utilisateur est en attente.  <br/> |Cette fonctionnalité est actuellement à l'étude, mais nous avons recueilli les derniers commentaires afin de la mettre en œuvre dans les prochaines mises à jour de service.  <br/> |Aucune solution.  <br/> |30/8/2017  <br/> |
|Un utilisateur Skype Entreprise Server (sur site) qui a affecté la licence d’audioconférence avant le 1er mars 2019 ne peut pas voir les coordonnées de numérotation dans ses invitations à la réunion.  <br/> |La mise en service des utilisateurs de Skype Entreprise Server pour l’audioconférence Teams n’était pas prise en charge avant cette date. Elle est désormais prise en charge et fait partie de [Réunions En premier.](https://docs.microsoft.com/microsoftteams/meetings-first) L’utilisateur doit avoir une licence Teams.  <br/> |Le pipeline d’approvisionnement doit être réactivé. Supprimez la licence d’audioconférence de l’utilisateur, attendez quelques heures, puis réattribuez la licence.  <br/> |1/3/2019  <br/> |
   
## <a name="related-topics"></a>Sujets associés

[Essayer ou acheter l’audioconférence dans Microsoft 365 ou Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
