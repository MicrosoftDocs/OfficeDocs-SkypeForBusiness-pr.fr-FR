---
title: Problèmes connus des Plans d’appel
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
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
ms.openlocfilehash: d201db80c2da09223d8e3b1935c383089f997382
ms.sourcegitcommit: f942232d43fc4ad56b34dd400fdb4bca39013f5f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="calling-plans-known-issues"></a>Problèmes connus des Plans d’appel

Plans d’appel dans Office 365 sont une nouvelle fonctionnalité trouvée dans Skype pour l’activité en ligne. Les éléments suivants sont des problèmes actuels qui sont suivies et activement examinée. Ils seront résolus potentiellement lorsque la fonction est mis à jour dans les versions futures dans Office 365 et Skype pour l’activité en ligne.
  
## <a name="calling-plans-known-issues"></a>Problèmes connus des Plans d’appel

|**Problème connu**|**Commentaires**|
|:-----|:-----|
|Transition à partir de Tech Preview des licences pour les licences de production pour les Plans d’appel de ne pas mettre à jour automatiquement la licence.  <br/> |Commencez par acheter vos nouvelles licences afin qu'elles soient prêtes pour être affectées à vos utilisateurs. Supprimer la licence de promotion (Tech Preview) d’un utilisateur, et d’affecter **immédiatement** les nouvelles licences **Intérieures appelant Plan** et/ou **national et International appel de planifier** à l’utilisateur. <br/> Si vous supprimez et ajoutez des licences pour plusieurs utilisateurs, il est très important de supprimer les licences de tous les utilisateurs à l'aide de Windows PowerShell, puis de leur affecter **IMMÉDIATEMENT** les nouvelles licences en utilisant là encore Windows PowerShell. Cela permet de garantir qu’il n’y a aucune interruption de service lors de la gestion des volumes importants d’attributions de licence d’utilisateur. Pour des exemples de scripts PowerShell, consultez [Affecter un Skype pour les professionnels et les équipes Microsoft des licences](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).  <br/> **Remarque :** Si vous utilisez la connectivité RTPC sur site pour les utilisateurs de hybride, vous *seulement* devez attribuer une licence de **Système téléphonique** . Il ne doit **pas** également attribuer une voix à l’appel de Plan. Toutefois, si vous activez l’appel de Plans dans Office 365 pour les utilisateurs qui se trouvent dans Office 365, vous devez toujours assigner un **Intérieur appel de planifier** ou une licence **national et International appelant planifier** pour les utilisateurs. Reportez-vous à la section [Affecter un Skype pour les professionnels et les équipes Microsoft des licences](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

> [!NOTE]
> Si vous avez besoin obtenir des numéros de téléphone supplémentaires que cela, veuillez [contacter le support technique pour les produits d’entreprise - aide de l’administrateur](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |
   
## <a name="related-topics"></a>Rubriques connexes
[Questions fréquentes à propos du transfert de numéros de téléphone](transferring-phone-numbers-common-questions.md)

[Différents types de numéros de téléphone utilisés pour les offres d'appel](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gérer des numéros de téléphone pour votre entreprise](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Conditions générales relatives aux appels d'urgence](../legal-and-regulatory/emergency-calling-terms-and-conditions.md)

[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 