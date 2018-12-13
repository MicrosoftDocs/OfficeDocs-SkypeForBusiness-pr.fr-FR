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
# <a name="update-aad-connect-to-include-more-than-one-forest"></a><span data-ttu-id="3a3c9-103">Mise à jour DAS se connecter à inclure plusieurs forêts</span><span class="sxs-lookup"><span data-stu-id="3a3c9-103">Update AAD Connect to include more than one forest</span></span>

<span data-ttu-id="3a3c9-104">Azure AD Connect prend en charge [la synchronisation de plusieurs forêts](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-topologies).</span><span class="sxs-lookup"><span data-stu-id="3a3c9-104">Azure AD Connect supports [syncing from multiple forests](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-topologies).</span></span> <span data-ttu-id="3a3c9-105">Toutefois, elle prend en charge qu’une seule instance de la synchronisation Azure AD Connect DAS.</span><span class="sxs-lookup"><span data-stu-id="3a3c9-105">However, it supports only one instance of Azure AD Connect syncing to AAD.</span></span> <span data-ttu-id="3a3c9-106">Par conséquent, dans les cas où Azure AD est déjà installé dans une forêt, l’instance existante de se connecter DAS doit être mis à jour pour la synchronisation de la forêt supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="3a3c9-106">Therefore, in cases where Azure AD is already installed in one forest, the existing instance of AAD Connect must be updated to sync from the additional forest.</span></span>

 - <span data-ttu-id="3a3c9-107">Si toutes les identités sont représentées qu’une seule fois dans les deux forêts (autrement dit, vous n’avez pas effectué les contacts à extension messagerie), vous pouvez simplement réexécuter l’Assistant de connexion DAS, choisissez « Personnaliser les options de synchronisation », et puis, sur le \*\*connecter vos annuaires \*\*page, entrez le nom de la forêt supplémentaire et creds.</span><span class="sxs-lookup"><span data-stu-id="3a3c9-107">If all identities are represented only once across both forests (that is, you haven’t made any mail-enabled contacts), then you can simply re-run the AAD Connect wizard, choose “Customize synchronization options,” and then on the **Connect Your Directories** page, enter the name of the additional forest and creds.</span></span><br><br>
 <span data-ttu-id="3a3c9-108">![La page de vos répertoires de se connecter](../media/cloud-consolidation-connect-your-directories.png)</span><span class="sxs-lookup"><span data-stu-id="3a3c9-108">![The Connect your directories page](../media/cloud-consolidation-connect-your-directories.png)</span></span>
 - <span data-ttu-id="3a3c9-109">Toutefois, si les utilisateurs peuvent exister dans plus un répertoire et que vous allez fusionner les données (par exemple, si des objets contact existent dans une forêt correspondant aux utilisateurs dans une autre forêt), vous devrez désinstaller Azure AD Connect et réinstallez-le.</span><span class="sxs-lookup"><span data-stu-id="3a3c9-109">However, if users can exist in more than one directory and you’ll be merging the data (for example, if contact objects exist in a forest corresponding to users in another forest), you will need to uninstall Azure AD Connect and re-install it.</span></span>  <span data-ttu-id="3a3c9-110">Il s’agit, car la condition de règles de jointure entre les forêts ne peut être configurée au cours de la première installation.</span><span class="sxs-lookup"><span data-stu-id="3a3c9-110">This is because the cross-forest join rules condition can only be configured during the first install.</span></span> <span data-ttu-id="3a3c9-111">Cette opération est effectuée sur la page suivante :</span><span class="sxs-lookup"><span data-stu-id="3a3c9-111">This is done on the following page:</span></span><br><br>
 <span data-ttu-id="3a3c9-112">![L’identifiant de votre page d’utilisateurs](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span><span class="sxs-lookup"><span data-stu-id="3a3c9-112">![The Uniquely identifying your users page](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span></span>


## <a name="see-also"></a><span data-ttu-id="3a3c9-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3a3c9-113">See also</span></span>

[<span data-ttu-id="3a3c9-114">Consolidation de cloud pour les équipes et Skype pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="3a3c9-114">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)