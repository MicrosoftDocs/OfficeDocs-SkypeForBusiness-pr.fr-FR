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
localization_priority: Normal
description: Cette annexe comprend des étapes détaillées pour la mise à jour d’AAD Connect afin d’inclure plusieurs forêts dans le cadre de la consolidation du cloud pour Teams et Skype Entreprise.
ms.openlocfilehash: a61a45c8a492afd761f8cc6b1020b591851645b8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049096"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a>Mettre à jour AAD Connect pour inclure plusieurs forêts

Azure AD Connect prend en charge [la synchronisation à partir de plusieurs forêts.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-topologies) Toutefois, il ne prend en charge qu’une seule instance d’Azure AD Connect synchronisée avec AAD. Par conséquent, dans les cas où Azure AD est déjà installé dans une forêt, l’instance existante d’AAD Connect doit être mise à jour pour être synchronisée à partir de la forêt supplémentaire.

 - Si toutes les identités ne sont représentées qu’une seule fois dans les deux forêts (c’est-à-dire que vous n’avez pas de contacts à messagerie), vous pouvez simplement ré-exécuter l’Assistant AAD Connect, choisir « Personnaliser les options de synchronisation », puis dans la **page** Connecter vos répertoires, entrez le nom de la forêt supplémentaire et ajoutez des creds.<br><br>
 ![Page Connecter vos annuaires](../media/cloud-consolidation-connect-your-directories.png)
 - Toutefois, si des utilisateurs peuvent exister dans plusieurs répertoires et que vous fusionnez les données (par exemple, si des objets contact existent dans une forêt correspondant aux utilisateurs d’une autre forêt), vous devrez désinstaller Azure AD Connect et le réinstaller.  Cela est dû au fait que la condition de règles de jointeur entre forêts ne peut être configurée que lors de la première installation. Pour ce faire, voir la page suivante :<br><br>
 ![Page Identifiant de manière unique vos utilisateurs](../media/cloud-consolidation-uniquely-identifying-your-users.png)


## <a name="see-also"></a>Voir aussi

[Consolidation du cloud pour Teams et Skype Entreprise](cloud-consolidation.md)