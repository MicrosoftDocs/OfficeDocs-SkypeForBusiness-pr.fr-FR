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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Obtenir la liste des problèmes connus lors de l’utilisation de Microsoft en tant que leur fournisseur de conférence rendez-vous, l’état et des solutions. '
ms.openlocfilehash: e5c6144081eb68426d3be53efb0ac9e9acbf41bd
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887460"
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a>Problèmes connus et dépannage à propos de l'audioconférence

 **Cet article est destiné Skype pour les utilisateurs professionnels et Teams Microsoft à l’aide de Microsoft en tant que leur fournisseur de services d’audioconférence. Il ne s’applique pas aux clients qui utilisent un fournisseur de services d’audioconférence tiers (ACP).**
  
## <a name="troubleshooting-and-known-issues"></a>Dépannage et problèmes connus

Les audioconférences qui utilisent Microsoft comme fournisseur d'audioconférence présentent des problèmes actuels qui font l'objet d'un suivi et d'une enquête active, et qui pourraient être résolus lorsque la fonctionnalité sera mise à jour dans les versions futures d'Office 365.
  
Pour l’instant, à utiliser comme référence lorsque vous essayez de résoudre les problèmes potentiels avec l’obtention de conférence Audio configurer et d’utilisation pour les personnes qui utilisent le Skype pour les applications métiers ou Teams Microsoft dans votre organisation.
  
### <a name="microsoft-teams-app"></a>Les équipes Microsoft application

|**Problème**|**Comportement/symptômes**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Les appelants RTC ayant le même numéro « De » sont affichés comme le même utilisateur dans la liste de présence de la réunion.  <br/> |Lorsque plusieurs appelants RTC rejoignent une réunion et que leurs identifications de l’appelant sont masquées sous la forme d'un numéro unique, ils s'affichent en tant qu'appelant unique dans la liste de présence de la réunion.  <br/> |Aucune solution.  <br/> |25/9/2017  <br/> |
|Le panneau d'information sur la réunion ne s'affiche pas de façon intermittente.  <br/> |Le panneau d'informations de réunion peut ne pas s'afficher dans le client Teams, lorsque les utilisateurs tentent de rechercher les numéros de téléphone du pont de conférence ou l'ID de conférence.  <br/> |Consultez les détails de la réunion ou le calendrier Outlook pour afficher les numéros de téléphone du pont de conférence ou l'ID de la conférence.  <br/> |25/9/2017  <br/> |
|Les invitations à des réunions à partir du complément Outlook affichent des caractères anormaux dans les coordonnées RTC pour les paramètres régionaux non américains.  <br/> |Lors de la planification de réunions privées à l'aide du complément Outlook pour Microsoft Teams sur un ordinateur avec des paramètres régionaux non américains, les coordonnées RTC peuvent contenir des caractères anormaux.  <br/> |Aucune solution.  <br/> |25/9/2017  <br/> |
|La sortie de numérotation doit utiliser 5 chiffres ou plus.  <br/> |Les utilisateurs qui tentent de composer un numéro à partir d'une réunion doivent taper 5 chiffres ou plus, même si la règle de normalisation du forfait de numérotation est disponible pour normaliser la numérotation des numéros courts à E.164.  <br/> |Appelez en tapant le numéro SDA complet ou le format de numéro local, au lieu du numéro de poste interne.  <br/> |25/9/2017  <br/> |
|Le contrôle d'appel sortant ne s'affiche pas de façon intermittente.  <br/> |Le contrôle d'appel sortant peut ne pas être visible à partir du panneau Informations sur la réunion.  <br/> |Aucune solution.  <br/> |25/9/2017  <br/> |
|L'ID de conférence statique n'est pas pris en charge pour les réunions Microsoft Teams.  <br/> |Si l'administrateur remplace le paramètre par défaut de l'ID de conférence dynamique par l'ID de conférence statique, ce paramètre ne s'applique pas aux réunions Microsoft Teams. Voir [ID dynamiques à l’aide de conférence dans votre organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md).  <br/> |Aucune solution.  <br/> |25/9/2017  <br/> |
|Les coordonnées de réunion RTC ne sont pas disponibles pour les utilisateurs locaux de Skype Entreprise.  <br/> |Si l'utilisateur est un utilisateur local de Skype Entreprise, à qui on a attribué Skype Entreprise Online, une audioconférence et des licences Teams, toutes les réunions programmées à l'aide de Teams n'incluront pas les coordonnées de réunion RTC. <br/> |Aucune solution.  <br/> |1/2/2018  <br/> |
   
### <a name="skype-for-business-app"></a>Application Skype Entreprise

|**Problème**|**Comportement/symptômes**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Notifications d’entrée et de sortie sont activées lorsque démarre une réunion, mais ils sont désactivés peu après le démarrage de la réunion.  <br/> |Par défaut, les notifications d’entrée et de sortie sont désactivées pour les réunions où les participants rejoignent à partir de deux Skype pour les applications métier et lorsqu’ils se connecter. Vous pouvez activer les annonces dans les **Options de réunion Skype** le Skype pour l’application de gestion. Dans le cadre d'une réunion où tous les participants doivent composer le numéro et rejoindre la réunion, les notifications d'entrée et de sortie sont activées par défaut, car les participants n'ont pas tous accès à la liste des participants. Lorsque une réunion a démarré avec uniquement les participants appel dans l’entrée et sortie notifications seront activées, mais lorsqu’un participant jointures à l’aide d’un Skype pour l’application de gestion, les notifications sera désactivé. Lorsque désactivée, les notifications peuvent être activées à l’aide **Des Options de réunion Skype** dans le Skype pour l’application de gestion. <br/> |Aucune solution.  <br/> |30/8/2017  <br/> |
|Si un utilisateur est mis en service la première fois par une licence E5 assignée, il est possible pour le message électronique de bienvenue audioconférence ne pas être remis à l’utilisateur si la boîte aux lettres n’est pas activé.  <br/> |Dans ce cas, vous pouvez toujours renvoyer les informations de conférence audio de l’utilisateur à l’aide de **conférence Audio** dans le Skype pour entreprise centre d’administration ou à l’aide de PowerShell. Consultez la rubrique [Activer ou désactiver l’envoi de messages électroniques lors de la modifient des paramètres de conférence Audio](enable-or-disable-sending-emails-when-their-settings-change.md).  <br/> **Remarque :** Afin de renvoyer le code confidentiel de conférence audio à l’utilisateur, le code confidentiel doit être réinitialisé. Il est également possible à l’aide de **conférence Audio** dans le Skype pour entreprise centre d’administration ou à l’aide de PowerShell.          |Aucune solution.  <br/> |30/8/2017  <br/> |
|Appels de conférence audio peuvent prendre jusqu'à 24 heures à afficher dans les rapports d’utilisation.  <br/> |Nous attendons améliorer de cette zone service futures mises à jour.  <br/> |Aucune solution.  <br/> |30/8/2017  <br/> |
|Lorsqu’un appelant appelle un pont de conférence après que la réunion a été verrouillée par une Skype pour l’utilisateur d’entreprise, il n’existe pas de notification dans le Skype pour Business application indiquant que l’utilisateur est en attente dans la salle d’attente.  <br/> |Cette fonctionnalité est actuellement à l'étude, mais nous avons recueilli les derniers commentaires afin de la mettre en œuvre dans les prochaines mises à jour de service.  <br/> |Aucune solution.  <br/> |30/8/2017  <br/> |
   
## <a name="related-topics"></a>Rubriques connexes

[Tester ou acheter l'audioconférence dans Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
