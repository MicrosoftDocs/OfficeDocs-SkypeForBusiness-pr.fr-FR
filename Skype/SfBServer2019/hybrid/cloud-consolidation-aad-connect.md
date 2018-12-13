---
title: Mise à jour DAS se connecter à inclure plusieurs forêts
ms.author: crowe
author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Cette annexe inclut des procédures détaillées pour mettre à jour DAS se connecter pour inclure plusieurs forêts dans le cadre de la consolidation de cloud pour les équipes et Skype pour les entreprises.
ms.openlocfilehash: d7229d54c159f7e07a233636f1576830e667dce5
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247647"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a>Mise à jour DAS se connecter à inclure plusieurs forêts

Azure AD Connect prend en charge [la synchronisation de plusieurs forêts](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-topologies). Toutefois, elle prend en charge qu’une seule instance de la synchronisation Azure AD Connect DAS. Par conséquent, dans les cas où Azure AD est déjà installé dans une forêt, l’instance existante de se connecter DAS doit être mis à jour pour la synchronisation de la forêt supplémentaire.

 - Si toutes les identités sont représentées qu’une seule fois dans les deux forêts (autrement dit, vous n’avez pas effectué les contacts à extension messagerie), vous pouvez simplement réexécuter l’Assistant de connexion DAS, choisissez « Personnaliser les options de synchronisation », et puis, sur le **connecter vos annuaires **page, entrez le nom de la forêt supplémentaire et creds.<br><br>
 ![La page de vos répertoires de se connecter](../media/cloud-consolidation-connect-your-directories.png)
 - Toutefois, si les utilisateurs peuvent exister dans plus un répertoire et que vous allez fusionner les données (par exemple, si des objets contact existent dans une forêt correspondant aux utilisateurs dans une autre forêt), vous devrez désinstaller Azure AD Connect et réinstallez-le.  Il s’agit, car la condition de règles de jointure entre les forêts ne peut être configurée au cours de la première installation. Cette opération est effectuée sur la page suivante :<br><br>
 ![L’identifiant de votre page d’utilisateurs](../media/cloud-consolidation-uniquely-identifying-your-users.png)


## <a name="see-also"></a>Voir aussi

[Consolidation de cloud pour les équipes et Skype pour les entreprises](cloud-consolidation.md)