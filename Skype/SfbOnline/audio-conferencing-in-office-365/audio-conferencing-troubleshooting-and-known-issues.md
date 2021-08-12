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
ms.openlocfilehash: ee47417941ae39eff966ab2a2d4eb0e07e7d451e404b95ddb66816c61be42664
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54301840"
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a>Problèmes connus et dépannage à propos de l'audioconférence

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

 **Cet article est réservé aux Skype Entreprise qui utilisent Microsoft comme fournisseur de services d’audioconférence. Il ne s’applique pas aux clients qui utilisent un fournisseur de services d’audioconférence (ACP) tiers.**
  
## <a name="troubleshooting-and-known-issues"></a>Dépannage et problèmes connus

L’audioconférence qui utilise Microsoft comme fournisseur de services d’audioconférence présente des problèmes actuels qui font l’objet d’un suivi et font l’objet de recherches et seront potentiellement résolus lorsque la fonctionnalité sera mise à jour dans les prochaines Microsoft 365.
  
Pour l’instant, utilisez cette référence pour résoudre les problèmes potentiels de mise en place et de fonctionnement de l’audioconférence pour les personnes qui utilisent Skype Entreprise dans votre organisation.

|**Problème**|**Comportement/symptômes**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Les notifications d’entrée et de sortie sont désactivées lorsqu’une réunion commence, mais elles sont désactivées peu de temps après le début de la réunion.  <br/> |Par défaut, les notifications d’entrée et de sortie sont désactivées pour les réunions que les participants rejoignent à partir des deux Skype Entreprise et lorsqu’ils composent le numéro. Vous pouvez activer les annonces dans les **options Réunion Skype’application** Skype Entreprise’application. Dans le cadre d'une réunion où tous les participants doivent composer le numéro et rejoindre la réunion, les notifications d'entrée et de sortie sont activées par défaut, car les participants n'ont pas tous accès à la liste des participants. Lorsqu’une réunion a commencé et que seuls des participants l’ont rejointe, les notifications d’entrée et de sortie sont désactivées, mais lorsqu’un participant rejoint la réunion à l’aide d’une application Skype Entreprise, les notifications sont désactivées. Lorsque les notifications sont désactivées, vous pouvez les activer de nouveau à l’aide **des options Réunion Skype dans** l’Skype Entreprise automatique. <br/> |Aucune solution.  <br/> |30/8/2017  <br/> |
|Si un utilisateur est mis en service pour la première fois en se faisant attribuer une licence E5, il est possible que l’audioconférence de bienvenue ne soit pas remis à l’utilisateur si la boîte aux lettres n’est pas activée.  <br/> |Dans ce cas, vous pouvez toujours renvoyer les informations d’audioconférence de l’utilisateur à l’aide de l’audioconférence dans le Skype Entreprise d’administration ou à l’aide de PowerShell.  Voir Activer ou désactiver l’envoi de courriers électroniques en cas de modification des [paramètres d’audioconférence.](enable-or-disable-sending-emails-when-their-settings-change.md)  <br/> **Remarque :** Pour renvoyer le code confidentiel de l’audioconférence à l’utilisateur, le code confidentiel doit être réinitialisé. Vous pouvez également utiliser **l’audioconférence** dans le Skype Entreprise d’administration ou PowerShell.          |Aucune solution.  <br/> |30/8/2017  <br/> |
|Les appels d’audioconférence peuvent prendre jusqu’à 24 heures pour s’afficher dans les rapports d’utilisation.  <br/> |Nous espérons apporter des améliorations dans ce domaine dans les prochaines mises à jour de service.  <br/> |Aucune solution.  <br/> |30/8/2017  <br/> |
|Lorsqu’un appelant appelle un pont de conférence après qu’un utilisateur Skype Entreprise a verrouillé la réunion, l’application Skype Entreprise n’Skype Entreprise pas avertissant que l’utilisateur est en attente.  <br/> |Cette fonctionnalité est actuellement à l'étude, mais nous avons recueilli les derniers commentaires afin de la mettre en œuvre dans les prochaines mises à jour de service.  <br/> |Aucune solution.  <br/> |30/8/2017  <br/> |
|Un Skype Entreprise Server (sur site) qui a affecté la licence d’audioconférence avant le 1er mars 2019 ne peut pas voir les coordonnées de numérotation dans ses invitations à la réunion.  <br/> |L’approvisionnement Skype Entreprise Server utilisateurs pour l Teams conférence audio n’a pas été pris en charge avant cette date. Il est désormais pris en charge et fait partie de [Réunions En premier.](/microsoftteams/meetings-first) L’utilisateur doit avoir une licence Teams utilisateur.  <br/> |Le pipeline d’approvisionnement doit être réactivé. Supprimez la licence d’audioconférence de l’utilisateur, attendez quelques heures, puis réattribuez la licence.  <br/> |1/3/2019  <br/> |
   
## <a name="related-topics"></a>Voir aussi

[Essayez ou achetez l’audioconférence dans Microsoft 365 ou Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
