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
description: 'Obtenez une liste des problèmes connus liés à l’utilisation de Microsoft comme fournisseur de conférences rendez-vous, ainsi que des solutions de contournement. '
ms.openlocfilehash: 6c462fea8a6ff1ebdae25a09ef8471d82559f3eb
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41695769"
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a>Problèmes connus et dépannage à propos de l'audioconférence

 **Cet article est destiné aux utilisateurs de Skype entreprise qui utilisent Microsoft comme fournisseur de services d’audioconférence. Cela ne s’applique pas aux clients qui utilisent un fournisseur de services d’audioconférence tiers.**
  
## <a name="troubleshooting-and-known-issues"></a>Dépannage et problèmes connus

Les audioconférences qui utilisent Microsoft comme fournisseur d'audioconférence présentent des problèmes actuels qui font l'objet d'un suivi et d'une enquête active, et qui pourraient être résolus lorsque la fonctionnalité sera mise à jour dans les versions futures d'Office 365.
  
Pour le moment, utilisez la documentation comme référence lorsque vous résolvez des problèmes potentiels liés à la configuration et à l’utilisation de Skype entreprise dans votre organisation.

|**Problème**|**Comportement/symptômes**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Les notifications d’entrée et de sortie sont activées lorsqu’une réunion commence, mais elles sont désactivées peu après le début de la réunion.  <br/> |Par défaut, les notifications d’entrée et de sortie sont désactivées pour les réunions auxquelles les participants participent à partir des applications Skype entreprise et lors de leur numérotation. Vous pouvez activer les annonces dans les **options de réunion Skype** dans l’application Skype entreprise. Dans le cadre d'une réunion où tous les participants doivent composer le numéro et rejoindre la réunion, les notifications d'entrée et de sortie sont activées par défaut, car les participants n'ont pas tous accès à la liste des participants. Lorsqu’une réunion a commencé avec uniquement les participants qui se connectent, les notifications d’entrée et de sortie sont activées, mais quand un participant se connecte à l’aide d’une application Skype entreprise, les notifications sont désactivées. Lorsque cette option est désactivée, les notifications peuvent être activées en utilisant les **options de réunion Skype** dans l’application Skype entreprise. <br/> |Aucune solution.  <br/> |30/8/2017  <br/> |
|Si un utilisateur est approvisionné pour la première fois en ayant reçu une licence E5, il est possible que le message de bienvenue de l’audioconférence ne soit pas remis à l’utilisateur si la boîte aux lettres n’est pas activée.  <br/> |Si tel est le cas, vous pouvez toujours renvoyer les informations de l’audioconférence de l’utilisateur à l’aide de l' **audioconférence** dans le centre d’administration Skype entreprise ou à l’aide de PowerShell. Voir [activer ou désactiver l’envoi de courriers lorsque les paramètres de conférence audio changent](enable-or-disable-sending-emails-when-their-settings-change.md).  <br/> **Remarque :** Pour envoyer à l’utilisateur le code confidentiel de l’audioconférence, le code confidentiel doit être réinitialisé. Vous pouvez également effectuer cette opération à l’aide de l' **audioconférence** dans le centre d’administration Skype entreprise ou à l’aide de PowerShell.          |Aucune solution.  <br/> |30/8/2017  <br/> |
|Les appels d’audioconférence peuvent être affichés dans les rapports d’utilisation jusqu’à 24 heures.  <br/> |Nous espérons apporter des améliorations à cette zone dans les prochaines mises à jour de service.  <br/> |Aucune solution.  <br/> |30/8/2017  <br/> |
|Lorsqu’un utilisateur appelle un pont de conférence une fois que la réunion a été verrouillée par un utilisateur de Skype entreprise, il n’y a pas de notification dans l’application Skype entreprise indiquant que l’utilisateur se trouve dans la salle d’attente.  <br/> |Cette fonctionnalité est actuellement à l'étude, mais nous avons recueilli les derniers commentaires afin de la mettre en œuvre dans les prochaines mises à jour de service.  <br/> |Aucune solution.  <br/> |30/8/2017  <br/> |
|Un utilisateur Skype entreprise Server (locaux) A attribué la licence d’audioconférence avant le 1er mars 2019, il est possible que les coordonnées de connexion apparaissent dans les invitations aux réunions.  <br/> |La mise en service des utilisateurs de Skype entreprise Server pour les conférences audio d’équipes n’était pas prise en charge jusqu’à cette date. Ce service est désormais pris en charge et est un composant des [réunions d’abord](https://docs.microsoft.com/microsoftteams/meetings-first). L’utilisateur doit avoir une licence Teams.  <br/> |Le pipeline de mise en service doit être réactivé. Supprimez la licence d’audioconférence de l’utilisateur, attendez quelques heures, puis réattribuez la licence.  <br/> |1/3/2019  <br/> |
   
## <a name="related-topics"></a>Rubriques connexes

[Tester ou acheter l’audioconférence dans Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
