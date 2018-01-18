---
title: "Problèmes connus des Plans d’appel"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Calling Plans
description: "Découvrez les problèmes connus avec le programme appelant pour Office 365 (appel RTC) et que vous pouvez faire à leur sujet. "
ms.openlocfilehash: 42b282bce7ba65dc4e053020970a02e71c98b5bd
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="calling-plans-known-issues"></a>Problèmes connus des Plans d’appel

Plans d’appel dans Office 365 sont une nouvelle fonctionnalité trouvée dans Skype pour l’activité en ligne. Les éléments suivants sont des problèmes actuels qui sont suivies et activement examinée. Ils seront résolus potentiellement lorsque la fonction est mis à jour dans les versions futures dans Office 365 et Skype pour l’activité en ligne.
  
## <a name="calling-plans-known-issues"></a>Problèmes connus des Plans d’appel

|**Problème connu**|**Commentaires**|
|:-----|:-----|
|Transition à partir de Tech Preview des licences pour les licences de production pour les Plans d’appel de ne pas mettre à jour automatiquement la licence.  <br/> |Achetez vos nouvelles licences tout d’abord afin qu’elles soient prêtes à affecter à vos utilisateurs. Supprimer la licence de promotion (Tech Preview) d’un utilisateur, et d’affecter **immédiatement** les nouvelles licences **Intérieures appelant Plan** et/ou **national et International appel de planifier** à l’utilisateur. <br/> Si vous êtes la suppression et l’ajout de licences pour plusieurs utilisateurs, il est extrêmement important que vous supprimez les licences de tous les utilisateurs à l’aide de Windows PowerShell et ensuite affecter **immédiatement** les licences pour tous les utilisateurs de Windows PowerShell. Cela permet de garantir qu’il n’y a aucune interruption de service lors de la gestion des volumes importants d’attributions de licence d’utilisateur. Pour des exemples de scripts PowerShell, consultez [Affecter un Skype pour les professionnels et les équipes Microsoft des licences](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).  <br/> **Remarque :** Si vous utilisez la connectivité RTPC sur site pour les utilisateurs de hybride, vous *seulement* devez attribuer une licence de **Système téléphonique** . Il ne doit **pas** également attribuer une voix à l’appel de Plan. Toutefois, si vous activez l’appel de Plans dans Office 365 pour les utilisateurs qui se trouvent dans Office 365, vous devez toujours assigner un **Intérieur appel de planifier** ou une licence **national et International appelant planifier** pour les utilisateurs. Reportez-vous à la section [Affecter un Skype pour les professionnels et les équipes Microsoft des licences](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

> [!NOTE]
> Si vous avez besoin obtenir des numéros de téléphone supplémentaires que cela, veuillez [contacter le support technique pour les produits d’entreprise - aide de l’administrateur](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |
   
## <a name="related-topics"></a>Rubriques connexes
[Transfert de questions courantes des numéros de téléphone](transferring-phone-numbers-common-questions.md)

[Différents types de numéros de téléphone utilisés pour les Plans d’appel](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gérer les numéros de téléphone pour votre organisation](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Conditions générales relatives aux appels d'urgence](emergency-calling-terms-and-conditions.md)

[Skype pour Business Online : étiquette de décharge de responsabilité d’appel d’urgence](https://go.microsoft.com/fwlink/?LinkID=692099)
