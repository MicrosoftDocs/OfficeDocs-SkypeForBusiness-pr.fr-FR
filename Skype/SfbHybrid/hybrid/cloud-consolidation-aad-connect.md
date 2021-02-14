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
# <a name="update-aad-connect-to-include-more-than-one-forest"></a><span data-ttu-id="de6ba-103">Mettre à jour AAD Connect pour inclure plusieurs forêts</span><span class="sxs-lookup"><span data-stu-id="de6ba-103">Update AAD Connect to include more than one forest</span></span>

<span data-ttu-id="de6ba-104">Azure AD Connect prend en charge [la synchronisation à partir de plusieurs forêts.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-topologies)</span><span class="sxs-lookup"><span data-stu-id="de6ba-104">Azure AD Connect supports [syncing from multiple forests](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-topologies).</span></span> <span data-ttu-id="de6ba-105">Toutefois, il ne prend en charge qu’une seule instance d’Azure AD Connect synchronisée avec AAD.</span><span class="sxs-lookup"><span data-stu-id="de6ba-105">However, it supports only one instance of Azure AD Connect syncing to AAD.</span></span> <span data-ttu-id="de6ba-106">Par conséquent, dans les cas où Azure AD est déjà installé dans une forêt, l’instance existante d’AAD Connect doit être mise à jour pour être synchronisée à partir de la forêt supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="de6ba-106">Therefore, in cases where Azure AD is already installed in one forest, the existing instance of AAD Connect must be updated to sync from the additional forest.</span></span>

 - <span data-ttu-id="de6ba-107">Si toutes les identités ne sont représentées qu’une seule fois dans les deux forêts (c’est-à-dire que vous n’avez pas de contacts à messagerie), vous pouvez simplement ré-exécuter l’Assistant AAD Connect, choisir « Personnaliser les options de synchronisation », puis dans la **page** Connecter vos répertoires, entrez le nom de la forêt supplémentaire et ajoutez des creds.</span><span class="sxs-lookup"><span data-stu-id="de6ba-107">If all identities are represented only once across both forests (that is, you haven’t made any mail-enabled contacts), then you can simply re-run the AAD Connect wizard, choose “Customize synchronization options,” and then on the **Connect Your Directories** page, enter the name of the additional forest and creds.</span></span><br><br>
 <span data-ttu-id="de6ba-108">![Page Connecter vos annuaires](../media/cloud-consolidation-connect-your-directories.png)</span><span class="sxs-lookup"><span data-stu-id="de6ba-108">![The Connect your directories page](../media/cloud-consolidation-connect-your-directories.png)</span></span>
 - <span data-ttu-id="de6ba-109">Toutefois, si des utilisateurs peuvent exister dans plusieurs répertoires et que vous fusionnez les données (par exemple, si des objets contact existent dans une forêt correspondant aux utilisateurs d’une autre forêt), vous devrez désinstaller Azure AD Connect et le réinstaller.</span><span class="sxs-lookup"><span data-stu-id="de6ba-109">However, if users can exist in more than one directory and you’ll be merging the data (for example, if contact objects exist in a forest corresponding to users in another forest), you will need to uninstall Azure AD Connect and re-install it.</span></span>  <span data-ttu-id="de6ba-110">Cela est dû au fait que la condition de règles de jointeur entre forêts ne peut être configurée que lors de la première installation.</span><span class="sxs-lookup"><span data-stu-id="de6ba-110">This is because the cross-forest join rules condition can only be configured during the first install.</span></span> <span data-ttu-id="de6ba-111">Pour ce faire, voir la page suivante :</span><span class="sxs-lookup"><span data-stu-id="de6ba-111">This is done on the following page:</span></span><br><br>
 <span data-ttu-id="de6ba-112">![Page Identifiant de manière unique vos utilisateurs](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span><span class="sxs-lookup"><span data-stu-id="de6ba-112">![The Uniquely identifying your users page](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span></span>


## <a name="see-also"></a><span data-ttu-id="de6ba-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="de6ba-113">See also</span></span>

[<span data-ttu-id="de6ba-114">Consolidation du cloud pour Teams et Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="de6ba-114">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)