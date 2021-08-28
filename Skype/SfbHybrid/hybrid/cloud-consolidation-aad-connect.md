---
title: Mettre à jour AAD Connect pour inclure plusieurs forêts
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
description: Cette annexe comprend des étapes détaillées pour mettre à jour les Connecter AAD afin d’inclure plusieurs forêts dans le cadre de la consolidation du cloud pour Teams et Skype Entreprise.
ms.openlocfilehash: e803ae1e41fd0e68a56e059bbaf398ee30f807f6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58625796"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a>Mettre à jour AAD Connect pour inclure plusieurs forêts

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Azure AD Connecter prend en [charge la synchronisation à partir de plusieurs forêts.](/azure/active-directory/connect/active-directory-aadconnect-topologies) Toutefois, il ne prend en charge qu’une seule instance d’Azure AD Connecter synchronisation avec AAD. Par conséquent, dans les cas où Azure AD est déjà installé dans une forêt, l’instance existante d’AAD Connecter doit être mise à jour pour être synchronisée à partir de la forêt supplémentaire.

 - Si toutes les identités ne sont représentées qu’une seule fois dans les deux forêts (c’est-à-dire que vous n’avez pas de contacts à messagerie), vous pouvez simplement ré-exécuter l’Assistant AAD Connecter, choisir « Personnaliser les options de synchronisation », puis dans la page **Connecter** Vos répertoires, entrez le nom de la forêt supplémentaire et ajoutez des informations.<br><br>
 ![Page Connecter répertoires](../media/cloud-consolidation-connect-your-directories.png)
 - Toutefois, si des utilisateurs peuvent exister dans plusieurs répertoires et que vous fusionnez les données (par exemple, si des objets contact existent dans une forêt correspondant aux utilisateurs d’une autre forêt), vous devrez désinstaller Azure AD Connecter et le réinstaller.  Cela est dû au fait que la condition de règles de jointeur entre forêts ne peut être configurée que lors de la première installation. Pour ce faire, voir la page suivante :<br><br>
 ![Page Identifiant de manière unique vos utilisateurs](../media/cloud-consolidation-uniquely-identifying-your-users.png)


## <a name="see-also"></a>Voir aussi

[Consolidation du cloud pour Teams et Skype Entreprise](cloud-consolidation.md)