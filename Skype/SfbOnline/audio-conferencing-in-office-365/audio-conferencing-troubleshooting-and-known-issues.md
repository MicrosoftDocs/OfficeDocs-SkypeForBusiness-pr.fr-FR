---
title: Résolution des problèmes audio de conférence et les problèmes connus
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 72979911-5319-4de2-a275-4dd9a0f44fe6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Obtenir une liste des problèmes connus lors de l’utilisation de Microsoft en tant que son fournisseur de conférences, l’état et des solutions de contournement. '
ms.openlocfilehash: 3748c6f60c04ea34f327eb371ba16f112a124287
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/03/2018
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a>Résolution des problèmes audio de conférence et les problèmes connus

 **Cet article est pour Skype pour les utilisateurs professionnels et Teams de Microsoft comme leur fournisseur de conférence audio à l’aide de Microsoft. Il ne s’applique pas aux clients qui utilisent un fournisseur de conférence audio de tiers (ACP).**
  
## <a name="troubleshooting-and-known-issues"></a>Problèmes connus et dépannage

Conférence audio qui utilise Microsoft comme le fournisseur de conférence audio présente des problèmes en cours qui sont suivis et activement examinée et seront éventuellement résolus lorsque la fonction est mis à jour dans les futures mises à jour d’Office 365.
  
Pour l’instant, l’utiliser comme référence lorsque vous dépannez des problèmes potentiels avec la mise en route d’audioconférence de configurer et de travail pour les personnes utilisant le Skype pour les applications d’entreprise ou Teams de Microsoft dans votre organisation.
  
### <a name="microsoft-teams-app"></a>Les équipes Microsoft app

|**Problème**|**Comportement/problèmes**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Appelants RTPC avec le même numéro « de » sont indiquées par le même utilisateur dans la liste de la réunion.  <br/> |Lorsque plusieurs appelants de RTPC joindre une réunion, et leurs ID de l’appelant est masqués sous la forme d’un nombre unique, ils s’affichent sous la forme d’un seul appelant dans la liste de la réunion.  <br/> |Aucune solution.  <br/> |9/25/2017  <br/> |
|Panneau d’informations de réunion n’est pas visible par intermittence.  <br/> |Panneau d’informations de réunion peut ne pas affiche dans le client des équipes lorsque les utilisateurs tentent de rechercher numéros de téléphone de conférence pont ou ID de conférence.  <br/> |Examinez les détails de la réunion ou le calendrier d’Outlook pour afficher les numéros de téléphone de conférence pont ou ID de conférence.  <br/> |9/25/2017  <br/> |
|Des invitations de réunion à partir d’Outlook Add-in affichent des caractères illisibles dans coordonnées RTPC pour des paramètres régionaux non américains.  <br/> |Lors de la planification des conférences privées à l’aide de complément Outlook pour Microsoft Teams sur un ordinateur avec les paramètres régionaux de hors des États-Unis, RTPC coordonnées peuvent contenir des caractères incorrects.  <br/> |Aucune solution.  <br/> |9/25/2017  <br/> |
|Numérotation doit utiliser au moins 5 chiffres.  <br/> |Utilisateurs qui tentent d’établir une connexion depuis une réunion devront de taper des chiffres 5 ou plus, même si la règle de normalisation de plan de numérotation n’est disponible pour normaliser les chiffres court à E.164.  <br/> |Appels sortants en tapant la complète numéro DID ou le format de numéro local au lieu du numéro de poste interne.  <br/> |9/25/2017  <br/> |
|Appels sortants de contrôle n’est pas visible par intermittence.  <br/> |Appels sortants de contrôle n’est peut-être pas visible dans le panneau d’informations sur la réunion.  <br/> |Aucune solution.  <br/> |9/25/2017  <br/> |
|ID de conférence statique non pris en charge pour les réunions de Teams de Microsoft.  <br/> |Si l’administrateur substitue le paramètre par défaut de l’ID de conférence dynamique pour l’ID de conférence statique, ce paramètre ne prend effet pour les réunions de Teams de Microsoft. Reportez-vous [à l’aide de l’audioconférence dynamique d’ID dans votre organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md).  <br/> |Aucune solution.  <br/> |9/25/2017  <br/> |
|Réunion de RTPC coordonnées ne sont pas disponibles pour Skype pour les utilisateurs professionnels sur site  <br/> |Si l’utilisateur est un Skype pour professionnels sur site utilisateur, assigné avec Skype pour Business Online, audioconférence et des licences d’équipes, toutes les conférences planifiées à l’aide des équipes n’incluent pas les coordonnées de la réunion de RTPC. <br/> |Aucune solution.  <br/> |2/1/2018  <br/> |
   
### <a name="skype-for-business-app"></a>Skype pour l’application d’entreprise

|**Problème**|**Comportement/problèmes**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Notifications d’entrée et de sortie sont activées lorsque la réunion démarre, mais qu’ils sont désactivés peu après le démarrage de la réunion.  <br/> |Par défaut, les notifications d’entrée et de sortie sont désactivées pour les réunions en cas de participation de participants à partir de deux Skype pour les applications métier et lorsqu’ils se connectent. Vous pouvez activer les annonces dans les **Options de la réunion Skype** dans le Skype pour l’application d’entreprise. Dans le cadre d'une réunion où tous les participants doivent composer le numéro et rejoindre la réunion, les notifications d'entrée et de sortie sont activées par défaut, car les participants n'ont pas tous accès à la liste des participants. Lorsqu’une réunion a démarré avec uniquement les participants dans l’entrée de l’appel et notifications de sortie seront activées, mais un participant jointures à l’aide d’un Skype pour une application métier, les notifications doivent être mis hors tension. Mise hors tension, les notifications peuvent être activées à l’aide de **Skype Options d’une réunion** dans le Skype pour l’application d’entreprise. <br/> |Aucune solution.  <br/> |8/30/2017  <br/> |
|Si un utilisateur est mis en service la première fois par une licence E5 assignée, il est possible de l’e-mail de bienvenue d’audioconférence à ne pas être remis à l’utilisateur si la boîte aux lettres n’est pas activée.  <br/> |Dans ce cas, vous pouvez toujours renvoyer les informations de conférence audio de l’utilisateur à l’aide **d’audioconférence** dans le Skype pour Business admin center ou à l’aide de PowerShell. Reportez-vous à la section [Activer ou désactiver l’envoi de messages électroniques lors de la modifient des paramètres d’audioconférence](enable-or-disable-sending-emails-when-their-settings-change.md).  <br/> **Remarque :** Pour renvoyer la code PIN de conférence audio à l’utilisateur, le code confidentiel doit être réinitialisé. Il est également possible à l’aide **d’audioconférence** dans le Skype pour le centre d’administration Business ou à l’aide de PowerShell.          |Aucune solution.  <br/> |8/30/2017  <br/> |
|Appels de conférence audio peuvent prendre jusqu'à 24 heures pour afficher dans les rapports d’utilisation.  <br/> |Nous attendons avec impatience améliorer de cette zone service futures mises à jour.  <br/> |Aucune solution.  <br/> |8/30/2017  <br/> |
|Lorsque l’appelant tente de se connecte à un pont de conférence après que la réunion a été verrouillée par un Skype pour l’utilisateur professionnel, il n’est pas une notification dans le Skype indication d’application métier que l’utilisateur attend dans la salle d’attente.  <br/> |Cette fonctionnalité est actuellement à l'étude, mais nous avons recueilli les derniers commentaires afin de la mettre en œuvre dans les prochaines mises à jour de service.  <br/> |Aucune solution.  <br/> |8/30/2017  <br/> |
   
## <a name="related-topics"></a>Rubriques connexes

[Tester ou acheter l'audioconférence dans Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
