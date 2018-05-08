---
title: Problèmes connus et dépannage de conférence audio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Obtenir la liste des problèmes connus lors de l’utilisation de Microsoft en tant que leur fournisseur de conférence rendez-vous, l’état et des solutions. '
ms.openlocfilehash: fb22149d2aca537f491c0c8d475059ec9f6bc506
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a>Problèmes connus et dépannage de conférence audio

 **Cet article est destiné Skype pour les utilisateurs professionnels et Teams Microsoft à l’aide de Microsoft en tant que leur fournisseur de services d’audioconférence. Il ne s’applique pas aux clients qui utilisent un fournisseur de services d’audioconférence tiers (ACP).**
  
## <a name="troubleshooting-and-known-issues"></a>Problèmes connus et résolution des problèmes

Services d’audioconférence par Microsoft comme le fournisseur de services d’audioconférence présente des problèmes en cours qui sont suivis et activement examiné et sont susceptibles de résolution lorsque la fonctionnalité est mis à jour dans les futures versions d’Office 365.
  
Pour l’instant, à utiliser comme référence lorsque vous essayez de résoudre les problèmes potentiels avec l’obtention de conférence Audio configurer et d’utilisation pour les personnes qui utilisent le Skype pour les applications métiers ou Teams Microsoft dans votre organisation.
  
### <a name="microsoft-teams-app"></a>Les équipes Microsoft application

|**Problème**|**Comportement/symptômes**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Les appelants PSTN avec le même numéro « From » sont affichés en tant que le même utilisateur dans la liste des participants de la réunion.  <br/> |Lorsque plusieurs appelants PSTN participer à une réunion, et leurs ID d’appelant est masqués sous la forme d’un seul numéro, ils s’affichent en tant qu’un appelant unique dans la liste de la réunion.  <br/> |Aucune solution.  <br/> |9/25/2017  <br/> |
|Panneau d’informations de réunion n’est pas visible par intermittence.  <br/> |Panneau d’informations de réunion peut ne pas affiche dans le client équipes lorsque les utilisateurs tentent de rechercher numéros de téléphone de pont de conférence ou ID de conférence.  <br/> |Examinez les détails de la réunion ou le calendrier Outlook pour afficher les numéros de téléphone de pont de conférence ou ID de conférence.  <br/> |9/25/2017  <br/> |
|Invitations de réunion à partir de complément Outlook affichent les caractères corrompus de coordonnées PSTN de paramètres régionaux non-US.  <br/> |Lorsque vous planifiez des réunions privées à l’aide de complément Outlook pour Microsoft Teams sur un ordinateur avec les paramètres régionaux non américains, coordonnées PSTN peuvent contenir des caractères corrompus.  <br/> |Aucune solution.  <br/> |9/25/2017  <br/> |
|Appels sortants doit utiliser au moins 5 chiffres.  <br/> |Les utilisateurs qui essaient d’émettre des appels sortants à partir d’une réunion devront taper des chiffres 5 ou plus, même si la règle de normalisation de plan de numérotation est disponible pour normaliser les chiffres courte à E.164.  <br/> |Numéroter en tapant le numéro DID complet ou le format de numéro local au lieu du numéro de poste interne.  <br/> |9/25/2017  <br/> |
|Appels sortants de contrôle n’est pas visible par intermittence.  <br/> |Appels sortants de contrôle n’est peut-être pas visible dans le panneau informations sur la réunion.  <br/> |Aucune solution.  <br/> |9/25/2017  <br/> |
|ID de conférence statique ne pas pris en charge pour les réunions Teams Microsoft.  <br/> |Si l’administrateur remplace le paramètre par défaut à partir de l’ID de conférence dynamique à l’ID de conférence statique, ce paramètre ne prend effet pour les réunions Teams Microsoft. Voir [ID dynamiques à l’aide de conférence dans votre organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md).  <br/> |Aucune solution.  <br/> |9/25/2017  <br/> |
|Conférence PSTN coordonnées ne sont pas disponibles pour Skype pour les utilisateurs locaux professionnels  <br/> |Si l’utilisateur est un Skype pour utilisateur local de Business, assigné avec Skype pour l’entreprise en ligne, conférence Audio et des licences d’équipes, toutes les réunions planifiées à l’aide des équipes n’incluent pas les coordonnées de conférence PSTN. <br/> |Aucune solution.  <br/> |1/2/2018  <br/> |
   
### <a name="skype-for-business-app"></a>Skype pour l’application de gestion

|**Problème**|**Comportement/symptômes**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Notifications d’entrée et de sortie sont activées lorsque démarre une réunion, mais ils sont désactivés peu après le démarrage de la réunion.  <br/> |Par défaut, les notifications d’entrée et de sortie sont désactivées pour les réunions où les participants rejoignent à partir de deux Skype pour les applications métier et lorsqu’ils se connecter. Vous pouvez activer les annonces dans les **Options de réunion Skype** le Skype pour l’application de gestion. Dans le cadre d'une réunion où tous les participants doivent composer le numéro et rejoindre la réunion, les notifications d'entrée et de sortie sont activées par défaut, car les participants n'ont pas tous accès à la liste des participants. Lorsque une réunion a démarré avec uniquement les participants appel dans l’entrée et sortie notifications seront activées, mais lorsqu’un participant jointures à l’aide d’un Skype pour l’application de gestion, les notifications sera désactivé. Lorsque désactivée, les notifications peuvent être activées à l’aide **Des Options de réunion Skype** dans le Skype pour l’application de gestion. <br/> |Aucune solution.  <br/> |30/8/2017  <br/> |
|Si un utilisateur est mis en service la première fois par une licence E5 assignée, il est possible pour le message électronique de bienvenue audioconférence ne pas être remis à l’utilisateur si la boîte aux lettres n’est pas activé.  <br/> |Dans ce cas, vous pouvez toujours renvoyer les informations de conférence audio de l’utilisateur à l’aide de **conférence Audio** dans le Skype pour entreprise centre d’administration ou à l’aide de PowerShell. Consultez la rubrique [Activer ou désactiver l’envoi de messages électroniques lors de la modifient des paramètres de conférence Audio](enable-or-disable-sending-emails-when-their-settings-change.md).  <br/> **Remarque :** Afin de renvoyer le code confidentiel de conférence audio à l’utilisateur, le code confidentiel doit être réinitialisé. Il est également possible à l’aide de **conférence Audio** dans le Skype pour entreprise centre d’administration ou à l’aide de PowerShell.          |Aucune solution.  <br/> |30/8/2017  <br/> |
|Appels de conférence audio peuvent prendre jusqu'à 24 heures à afficher dans les rapports d’utilisation.  <br/> |Nous attendons améliorer de cette zone service futures mises à jour.  <br/> |Aucune solution.  <br/> |30/8/2017  <br/> |
|Lorsqu’un appelant appelle un pont de conférence après que la réunion a été verrouillée par une Skype pour l’utilisateur d’entreprise, il n’existe pas de notification dans le Skype pour Business application indiquant que l’utilisateur est en attente dans la salle d’attente.  <br/> |Cette fonctionnalité est actuellement à l'étude, mais nous avons recueilli les derniers commentaires afin de la mettre en œuvre dans les prochaines mises à jour de service.  <br/> |Aucune solution.  <br/> |30/8/2017  <br/> |
   
## <a name="related-topics"></a>Rubriques connexes

[Tester ou acheter l'audioconférence dans Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
