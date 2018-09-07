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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: "Obtenez une liste des problèmes connus lors de l'utilisation de Microsoft comme fournisseur de conférence téléphonique, statut et quelques solutions de contournement. "
ms.openlocfilehash: 6a8988145e9f07e0f110e5e9aa3b6976fbc570c4
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850078"
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a>Problèmes connus et dépannage à propos de l'audioconférence

 **Cet article s'adresse aux utilisateurs de Skype Entreprise et Microsoft Teams utilisant Microsoft comme fournisseur d'audioconférence. Il ne s'applique pas aux clients qui utilisent les services d'un fournisseur tiers de services d'audioconférence (ACP).**
  
## <a name="troubleshooting-and-known-issues"></a>Dépannage et problèmes connus

Les audioconférences qui utilisent Microsoft comme fournisseur d'audioconférence présentent des problèmes actuels qui font l'objet d'un suivi et d'une enquête active, et qui pourraient être résolus lorsque la fonctionnalité sera mise à jour dans les versions futures d'Office 365.
  
Pour l'instant, utilisez ceci comme référence lorsque vous dépannez des problèmes potentiels liés à la configuration et au fonctionnement de l'audioconférence pour les personnes utilisant les applications Skype Entreprise ou Microsoft Teams dans votre organisation.
  
### <a name="microsoft-teams-app"></a>Application Microsoft Teams

|**Problème**|**Comportement/symptômes**|**Solution de contournement connue**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Les appelants RTC ayant le même numéro « De » sont affichés comme le même utilisateur dans la liste de présence de la réunion.  <br/> |Lorsque plusieurs appelants RTC rejoignent une réunion et que leurs identifications de l’appelant sont masquées sous la forme d'un numéro unique, ils s'affichent en tant qu'appelant unique dans la liste de présence de la réunion.  <br/> |Aucune solution de contournement.  <br/> |25/9/2017  <br/> |
|Le panneau d'information sur la réunion ne s'affiche pas de façon intermittente.  <br/> |Le panneau d'informations de réunion peut ne pas s'afficher dans le client Teams, lorsque les utilisateurs tentent de rechercher les numéros de téléphone du pont de conférence ou l'ID de conférence.  <br/> |Consultez les détails de la réunion ou le calendrier Outlook pour afficher les numéros de téléphone du pont de conférence ou l'ID de la conférence.  <br/> |25/9/2017  <br/> |
|Les invitations à des réunions à partir du complément Outlook affichent des caractères anormaux dans les coordonnées RTC pour les paramètres régionaux non américains.  <br/> |Lors de la planification de réunions privées à l'aide du complément Outlook pour Microsoft Teams sur un ordinateur avec des paramètres régionaux non américains, les coordonnées RTC peuvent contenir des caractères anormaux.  <br/> |Aucune solution de contournement.  <br/> |25/9/2017  <br/> |
|La sortie de numérotation doit utiliser 5 chiffres ou plus.  <br/> |Les utilisateurs qui tentent de composer un numéro à partir d'une réunion doivent taper 5 chiffres ou plus, même si la règle de normalisation du forfait de numérotation est disponible pour normaliser la numérotation des numéros courts à E.164.  <br/> |Appelez en tapant le numéro SDA complet ou le format de numéro local, au lieu du numéro de poste interne.  <br/> |25/9/2017  <br/> |
|Le contrôle d'appel sortant ne s'affiche pas de façon intermittente.  <br/> |Le contrôle d'appel sortant peut ne pas être visible à partir du panneau Informations sur la réunion.  <br/> |Aucune solution de contournement.  <br/> |25/9/2017  <br/> |
|L'ID de conférence statique n'est pas pris en charge pour les réunions Microsoft Teams.  <br/> |Si l'administrateur remplace le paramètre par défaut de l'ID de conférence dynamique par l'ID de conférence statique, ce paramètre ne s'applique pas aux réunions Microsoft Teams. Voir [Utilisation des ID dynamiques d'audioconférence dans votre organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md).  <br/> |Aucune solution de contournement.  <br/> |25/9/2017  <br/> |
|Les coordonnées de réunion RTC ne sont pas disponibles pour les utilisateurs locaux de Skype Entreprise.  <br/> |Si l'utilisateur est un utilisateur local de Skype Entreprise, à qui on a attribué Skype Entreprise Online, une audioconférence et des licences Teams, toutes les réunions programmées à l'aide de Teams n'incluront pas les coordonnées de réunion RTC. <br/> |Aucune solution de contournement.  <br/> |1/2/2018  <br/> |
   
### <a name="skype-for-business-app"></a>Application Skype Entreprise

|**Problème**|**Comportement/symptômes**|**Solution de contournement connue**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Les notifications d'entrée et de sortie sont effectuées au début d'une réunion, mais elles sont désactivées peu après le début de la réunion.  <br/> |Par défaut, les notifications d'entrée et de sortie sont désactivées pour les réunions auxquelles les participants se joignent depuis Skype Entreprise et lorsqu'ils se connectent. Vous pouvez activer les annonces dans les **Options de Réunion Skype** de l'application Skype Entreprise. Dans le cadre d'une réunion où tous les participants doivent composer le numéro et rejoindre la réunion, les notifications d'entrée et de sortie sont activées par défaut, car les participants n'ont pas tous accès à la liste des participants. Lorsqu'une réunion a commencé avec uniquement des participants qui appellent, les notifications d'entrée et de sortie sont activées, mais lorsqu'un participant se joint à l'aide d'une application Skype Entreprise, les notifications sont désactivées. Lorsque les notifications sont désactivées, elles peuvent être réactivées à l'aide des **Options de Réunion Skype** de l'application Skype Entreprise. <br/> |Aucune solution de contournement.  <br/> |30/8/2017  <br/> |
|Si un utilisateur est approvisionné pour la première fois par l'attribution d'une licence E5, il est possible que l'e-mail de bienvenue de l'audioconférence ne soit pas envoyé à l'utilisateur, si la boîte aux lettres n'est pas activée.  <br/> |Dans ce cas, vous pouvez toujours renvoyer les informations d'audioconférence de l’utilisateur à l’aide de l'option **audioconférence** du centre d'administration de Skype Entreprise ou à l'aide de PowerShell. Voir [Activer ou désactiver l'envoi d'e-mails lorsque les paramètres de l'audioconférence changent](enable-or-disable-sending-emails-when-their-settings-change.md).  <br/> **Remarque :** Pour renvoyer le code confidentiel de l'audioconférence à l'utilisateur, le code confidentiel doit être réinitialisé. Pour ce faire, vous pouvez également utiliser **l'audioconférence** dans le centre d'administration de Skype Entreprise ou en utilisant PowerShell.          |Aucune solution de contournement.  <br/> |30/8/2017  <br/> |
|Les appels d'audioconférence peuvent prendre jusqu'à 24 heures pour apparaître dans les rapports d'utilisation.  <br/> |Nous espérons apporter des améliorations en la matière dans les prochaines mises à jour de service.  <br/> |Aucune solution de contournement.  <br/> |30/8/2017  <br/> |
|Lorsqu'un appelant se connecte à un pont de conférence après que la réunion a été verrouillée par un utilisateur Skype Entreprise, il n'y a pas de notification dans l'application Skype Entreprise indiquant que l'utilisateur attend dans le hall.  <br/> |Cette fonctionnalité est actuellement à l'étude, mais nous avons recueilli les derniers avis pour la mettre en œuvre dans les prochaines mises à jour de service.  <br/> |Aucune solution de contournement.  <br/> |30/8/2017  <br/> |
   
## <a name="related-topics"></a>Rubriques connexes

[Testez ou achetez l'audioconférence dans Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
