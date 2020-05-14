---
title: Problèmes connus relatifs aux forfaits d’appel
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Calling Plans
description: Découvrez les problèmes connus avec le plan d’appels pour les appels RTC et ce que vous pouvez faire à ce sujet.
ms.openlocfilehash: 3a97057f61c154ded83b85becbfcf53dc2b4bc78
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220734"
---
# <a name="calling-plans-known-issues"></a>Problèmes connus relatifs aux forfaits d’appel

Les plans d’appel constituent une nouvelle fonctionnalité de Skype entreprise online. Vous trouverez ci-après les problèmes actuellement suivis et examinés activement. Ils seront potentiellement résolus lorsque la fonctionnalité sera mise à jour dans les versions ultérieures.
  
## <a name="calling-plans-known-issues"></a>Problèmes connus relatifs aux forfaits d’appel

|**Problème connu**|**Commentaires**|
|:-----|:-----|
|La transition des licences Tech Preview aux licences de production pour les offres d’appels ne met pas automatiquement à jour la licence.  <br/> |Commencez par acheter vos nouvelles licences afin qu'elles soient prêtes pour être affectées à vos utilisateurs. Supprimez la licence promotion (Technical Preview) d’un utilisateur, puis affectez **immédiatement** le nouveau **plan d’appels nationaux** et/ou les licences de **plan d’appels nationaux et internationaux** à l’utilisateur. <br/> Si vous supprimez et ajoutez des licences pour plusieurs utilisateurs, il est très important de supprimer les licences de tous les utilisateurs à l'aide de Windows PowerShell, puis de leur affecter **IMMÉDIATEMENT** les nouvelles licences en utilisant là encore Windows PowerShell. Ainsi, vous garantirez qu’il n’y a aucune perturbation en service lors de la gestion d’un grand nombre d’attributions de licences utilisateur. Pour obtenir des exemples de scripts PowerShell, consultez la rubrique [affectation de licences Skype entreprise et Microsoft teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).  <br/> **Remarque :** Si vous utilisez une connectivité PSTN locale pour les utilisateurs hybrides *, il vous suffit d'* affecter une licence de **système téléphonique** . Vous ne devez **pas non** plus affecter de plan d’appels vocaux. Toutefois, si vous activez les offres d’appels dans Microsoft 365 ou Office 365 pour les utilisateurs qui se trouvent dans Microsoft 365 ou Office 365, vous devez quand même affecter une licence de plan d’appel **national** ou **international** à ces utilisateurs. Consultez la rubrique [affectation de licences Skype entreprise et Microsoft teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

> [!NOTE]
> Si vous avez besoin d’obtenir plus de numéros de téléphone, [Contactez le support technique pour les produits pour les entreprises-aide de l’administrateur](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |
   
## <a name="related-topics"></a>Rubriques connexes
[Questions fréquentes à propos du transfert de numéros de téléphone](/microsoftteams/transferring-phone-numbers-common-questions)

[Différents types de numéros de téléphone utilisés pour les offres d'appel](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Gérer des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[Conditions générales relatives aux appels d'urgence](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
