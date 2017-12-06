---
title: "Problèmes connus de Plans de l'appel"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: troubleshooting
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0

description: "Learn known issues with the calling plan for Office 365 (PSTN Calling) and what you can do about them. "
---

# Problèmes connus de Plans de l'appel

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'[avertissement](baa3645a-0518-472e-942e-971c63ba4ca0.md#MT_Footer). Vous pouvez consulter la version en anglais de cet article [ici](https://support.office.com/en-us/article/baa3645a-0518-472e-942e-971c63ba4ca0). 
  
Plans d'appel dans Office 365 sont une nouvelle fonctionnalité figurant dans Skype Entreprise Online. Les éléments suivants sont des problèmes connus qui sont suivies et ces activement examiné. Ils seront potentiellement résolues lorsque la fonctionnalité est mis à jour dans les versions futures dans Office 365 et Skype Entreprise Online.
  
## Problèmes connus de Plans de l'appel

|**Problème connu**|**Commentaires**|
|:-----|:-----|
|Transition à partir de Tech Preview des licences à des licences de production pour l'appel d'offre n'automatiquement à jour la licence.  <br/> |Acheter tout d'abord vos nouvelles licences afin qu'elles soient prêts à être affectées à vos utilisateurs. Supprimer la licence promotionnel (Tech Preview) d'un utilisateur et puis **immédiatement** assignez le nouveau **Nationaux appelant planifier** et/ou **International appelant planifier** des licences à l'utilisateur. <br/> Si vous êtes suppression et ajout de licences pour plusieurs utilisateurs, il est très important que vous supprimez les licences de tous les utilisateurs à l'aide de Windows PowerShell et puis attribuer **immédiatement** les licences pour tous les utilisateurs également à l'aide de Windows PowerShell. Vous garantissez ainsi qu'il n'existe aucune interruption de service lors de la gestion des volumes importants d'attributions de licences utilisateur. Pour les exemples de scripts PowerShell, voir[Attribuez Skype pour les entreprises et Microsoft Teams des licences](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).  <br/> > [!NOTE]> Si vous utilisez la connectivité PSTN en local pour les utilisateurs hybride, vous  *seulement*  devez attribuer une licence **Système téléphonique**. Vous ne devez **pas** également attribuer une voix planifier l'appel.> Toutefois, si vous activez l'appel d'offre dans Office 365 pour les utilisateurs qui se trouvent dans Office 365, vous devez toujours attribuer une licence **Appels nationaux appelant planifier** et/ou **International appelant planifier** pour les utilisateurs. Voir[Attribuez Skype pour les entreprises et Microsoft Teams des licences](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).           |
   
## Rubriques connexes

[Conditions générales relatives aux appels d'urgence](emergency-calling-terms-and-conditions.md)
  
[Période de sortant gratuit de audio conférence](../accessibility-and-regulatory/audio-conferencing-complimentary-dial-out-period.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  

