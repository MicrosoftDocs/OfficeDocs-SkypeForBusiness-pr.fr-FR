---
title: Mettre à jour le certificat de Microsoft Edge
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
description: Cette annexe comprend des étapes détaillées pour la mise à jour du certificat Edge dans le cadre de la consolidation du cloud pour Teams et Skype Entreprise.
ms.openlocfilehash: 3e6b151e340a0942b561edd2233795fad94c3a9e
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888603"
---
# <a name="update-the-edge-certificate"></a><span data-ttu-id="c32e5-103">Mettre à jour le certificat de Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c32e5-103">Update the edge certificate</span></span>

<span data-ttu-id="c32e5-104">La mise à jour du certificat edge est l’étape clé pour s’assurer qu’un environnement local avec SipDomain1 peut rejoindre un environnement cloud avec SipDomain2 et garantir un routage correct dans un environnement d’espace d’adressas partagé entre les deux domaines SIP.</span><span class="sxs-lookup"><span data-stu-id="c32e5-104">Updating the edge certificate is the key step to ensuring that an on-prem environment with SipDomain1 can join a cloud environment with SipDomain2 and ensure proper routing in a shared address space environment across the two SIP domains.</span></span> <span data-ttu-id="c32e5-105">Consultez l’étape 14 de [la consolidation cloud](cloud-consolidation.md) pour Teams et Skype Entreprise pour le contexte dans lequel vous pouvez effectuer cette étape.</span><span class="sxs-lookup"><span data-stu-id="c32e5-105">See step 14 in [Cloud consolidation for Teams and Skype for Business](cloud-consolidation.md) for context in which you might perform this step.</span></span> <span data-ttu-id="c32e5-106">Dans nos exemples, SipDomain1 est AcquiredCompany. <span> com et SipDomain2 est OriginalCompany. <span> com.</span><span class="sxs-lookup"><span data-stu-id="c32e5-106">In our examples, SipDomain1 is AcquiredCompany.<span>com and SipDomain2 is OriginalCompany.<span>com.</span></span>

<span data-ttu-id="c32e5-107">L’autre nom de sujet (SAN) du certificat sur tous les serveurs Edge dans l’environnement local doit être mis à jour pour inclure tous les domaines SIP existant dans le client en ligne pur (à l’exception de toute onmicrosoft. <span> com domains), sous la forme « sip. \< domaine> ».</span><span class="sxs-lookup"><span data-stu-id="c32e5-107">The subject alternate name (SAN) of the certificate on all edge servers in the on-premises environment must be updated to include all SIP domains that exist in the pure online tenant (excluding any onmicrosoft.<span>com domains), in the form “sip.\<domain>”.</span></span>  <span data-ttu-id="c32e5-108">Dans notre exemple, il s’agit de sip. OriginalCompany. <span> com.</span><span class="sxs-lookup"><span data-stu-id="c32e5-108">In our example, this is sip.OriginalCompany.<span>com.</span></span> <span data-ttu-id="c32e5-109">Cette étape est essentielle avant de migrer des utilisateurs vers le cloud.</span><span class="sxs-lookup"><span data-stu-id="c32e5-109">This step is critical to do before migrating any users to the cloud.</span></span>

<span data-ttu-id="c32e5-110">**Procédure :**</span><span class="sxs-lookup"><span data-stu-id="c32e5-110">**Steps:**</span></span>

1.  <span data-ttu-id="c32e5-111">Obtenez un nouveau certificat Edge externe pour le edge qui possède toutes les entrées existantes, ainsi que des entrées supplémentaires dans le SAN pour tous les domaines SIP dans l’environnement cloud (à l’exception des domaines \*.onmicrosoft.com) sous la forme « sip. ». <DomainName></span><span class="sxs-lookup"><span data-stu-id="c32e5-111">Obtain a new External Edge certificate for the edge that has all existing entries plus additional entries in the SAN for all SIP domains in the cloud environment (excluding \*.onmicrosoft.com domains) in the form “sip.<DomainName>”.</span></span>
2.  <span data-ttu-id="c32e5-112">Installez le certificat localement sur chaque serveur Edge et affectez-le au service Skype Edge sur chacun d’eux.</span><span class="sxs-lookup"><span data-stu-id="c32e5-112">Install the certificate locally on each edge server and assign it to the Skype Edge service on each of the edge service.</span></span>  <span data-ttu-id="c32e5-113">Pour obtenir la procédure détaillée, voir la section « Certificats d’interface Edge externe » dans [Deploy Edge Service in Skype for Business Server 2015](https://technet.microsoft.com/library/dn951368.aspx).</span><span class="sxs-lookup"><span data-stu-id="c32e5-113">For detailed steps, see the section “External Edge interface certificates” in [Deploy Edge Service in Skype for Business Server 2015](https://technet.microsoft.com/library/dn951368.aspx).</span></span>
3.  <span data-ttu-id="c32e5-114">Redémarrez le service Edge sur chacun des serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="c32e5-114">Restart the Edge service on each of the edge servers.</span></span> <span data-ttu-id="c32e5-115">Vous pouvez le faire pour une zone unique avec les commandes PowerShell suivantes :</span><span class="sxs-lookup"><span data-stu-id="c32e5-115">You can do this for a single box with the following PowerShell commands:</span></span>

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a><span data-ttu-id="c32e5-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c32e5-116">See also</span></span>

[<span data-ttu-id="c32e5-117">Consolidation du cloud pour Teams et Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="c32e5-117">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)