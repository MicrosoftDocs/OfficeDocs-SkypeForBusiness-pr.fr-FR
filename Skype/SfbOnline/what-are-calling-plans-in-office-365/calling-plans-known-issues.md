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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Calling Plans
description: Découvrez les problèmes connus concernant le plan d’appel pour les appels PSTN et ce que vous pouvez faire à leur sujet.
ms.openlocfilehash: f118f6107887dae00f640a15bcef625f91079bcc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58624466"
---
# <a name="calling-plans-known-issues"></a>Problèmes connus relatifs aux forfaits d’appel

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Les forfaits d’appels sont une nouvelle fonctionnalité de Skype Entreprise Online. Voici les problèmes actuels qui font l’objet d’un suivi et font l’objet de recherches actives. Ils seront potentiellement résolus lorsque la fonctionnalité sera mise à jour dans les prochaines builds.
  
## <a name="calling-plans-known-issues"></a>Problèmes connus relatifs aux forfaits d’appel

|**Problème connu**|**Commentaires**|
|:-----|:-----|
|La transition des licences Tech Preview aux licences de production pour les plans d’appels ne met pas automatiquement à jour la licence.  <br/> |Commencez par acheter vos nouvelles licences afin qu'elles soient prêtes pour être affectées à vos utilisateurs. Supprimez la licence de promotion (Tech  Preview) d’un utilisateur,  puis affectez IMMÉDIATEment les nouvelles licences Plan d’appels nationaux et/ou Plan d’appels nationaux et internationaux à l’utilisateur.  <br/> Si vous supprimez et ajoutez des licences pour plusieurs utilisateurs, il est très important de supprimer les licences de tous les utilisateurs à l'aide de Windows PowerShell, puis de leur affecter **IMMÉDIATEMENT** les nouvelles licences en utilisant là encore Windows PowerShell. Ainsi, vous vous assurerez qu’il n’y a aucune interruption de service lorsque vous traitez un grand nombre d’attributions de licences utilisateur. Pour consulter des exemples de scripts PowerShell, voir [Attribuer Skype Entreprise et Microsoft Teams licences.](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)  <br/> **Remarque :** Si vous utilisez la connectivité PSTN sur site  pour des utilisateurs hybrides, vous devez seulement affecter **une licence Système téléphonique** hybride. Vous ne devez **PAS** non plus affecter de plan d’appel vocal. Toutefois, si vous activez les plans d’appels dans Microsoft 365 ou Office 365 pour les utilisateurs qui  se trouveraient  dans Microsoft 365 ou Office 365, vous devez encore affecter une licence Plan d’appels nationaux ou nationaux et internationaux à ces utilisateurs. Voir [Attribuer Skype Entreprise et Microsoft Teams licences.](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)

> [!NOTE]
> Si vous devez obtenir plus de numéros de téléphone, contactez le support technique pour les [produits pour les entreprises - Aide de l’administrateur](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |
   
## <a name="related-topics"></a>Rubriques connexes
[Questions fréquentes à propos du transfert de numéros de téléphone](/microsoftteams/transferring-phone-numbers-common-questions)

[Différents types de numéros de téléphone utilisés pour les offres d'appel](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Gérer des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[Conditions générales relatives aux appels d'urgence](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
