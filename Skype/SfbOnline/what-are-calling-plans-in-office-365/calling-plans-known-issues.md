---
title: Problèmes connus relatifs aux forfaits d'appels
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 'Learn known issues with the calling plan for Office 365 (PSTN Calling) and what you can do about them. '
ms.openlocfilehash: e43aecea6bd19c6b346de68577f471214818d43f
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23854156"
---
# <a name="calling-plans-known-issues"></a>Problèmes connus relatifs aux forfaits d'appels

Plans d’appel dans Office 365 sont une nouvelle fonctionnalité trouvée dans Skype pour l’entreprise en ligne. Voici les problèmes en cours qui sont suivis et activement analysés. Ils seront potentiellement résolues lorsque la fonctionnalité est mis à jour dans les versions futures dans Office 365 et Skype pour Business Online.
  
## <a name="calling-plans-known-issues"></a>Problèmes connus relatifs aux forfaits d'appels

|**Problème connu**|**Commentaires**|
|:-----|:-----|
|Transition d’aperçu technique des licences pour les licences de production pour l’appel des Plans de ne pas mettre automatiquement à jour la licence.  <br/> |Commencez par acheter vos nouvelles licences afin qu'elles soient prêtes pour être affectées à vos utilisateurs. Supprimer la licence de promotion (aperçu technique) d’un utilisateur, puis affecter les nouvelles licences **Nationales appelant planifier** et/ou **national et International appelant planifier** **immédiatement** à l’utilisateur. <br/> Si vous supprimez et ajoutez des licences pour plusieurs utilisateurs, il est très important de supprimer les licences de tous les utilisateurs à l'aide de Windows PowerShell, puis de leur affecter **IMMÉDIATEMENT** les nouvelles licences en utilisant là encore Windows PowerShell. Cela permet de garantir qu’il n’existe aucune interruption de service lors de la gestion des volumes importants d’affectations de licence utilisateur. Pour des exemples de scripts PowerShell, voir [Attribuer de Skype pour les professionnels et les équipes Microsoft de licences](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).  <br/> **Remarque :** Si vous utilisez une connectivité PSTN sur site pour les utilisateurs hybride, vous *seulement* devez attribuer une licence de **Système téléphonique** . Il ne doit **pas** également attribuer une voix planifier l’appel. Toutefois, si vous activez des Plans de l’appel dans Office 365 pour les utilisateurs qui se trouvent dans Office 365, vous devez toujours attribuer un **Intérieur appelant planifier** ou une licence **national et International appelant planifier** pour les utilisateurs. Voir [Assigner de Skype pour les professionnels et les équipes Microsoft de licences](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

> [!NOTE]
> Si vous avez besoin obtenir les numéros de téléphone plus grand que cette, contactez le [support pour les produits métiers : aide d’administration](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |
   
## <a name="related-topics"></a>Rubriques connexes
[Questions fréquentes à propos du transfert de numéros de téléphone](/microsoftteams/transferring-phone-numbers-common-questions)

[Différents types de numéros de téléphone utilisés pour les offres d'appel](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Gérer des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[Conditions générales relatives aux appels d'urgence](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 