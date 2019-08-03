---
title: Mettre à jour le certificat de serveur Edge
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
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Cette annexe inclut des étapes détaillées pour mettre à jour le certificat de serveur Edge dans le cadre de la consolidation du Cloud pour teams et Skype entreprise.
ms.openlocfilehash: 1c3aaa8859db530ceccbebc68ae76f21e8d4a77f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36160519"
---
# <a name="update-the-edge-certificate"></a><span data-ttu-id="b18d5-103">Mettre à jour le certificat de serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b18d5-103">Update the edge certificate</span></span>

<span data-ttu-id="b18d5-104">La mise à jour du certificat de serveur Edge est l’étape essentielle pour s’assurer qu’un environnement local avec SipDomain1 peut rejoindre un environnement Cloud avec SipDomain2 et garantir le routage approprié dans un environnement d’espace d’adressage partagé dans les deux domaines SIP.</span><span class="sxs-lookup"><span data-stu-id="b18d5-104">Updating the edge certificate is the key step to ensuring that an on-prem environment with SipDomain1 can join a cloud environment with SipDomain2 and ensure proper routing in a shared address space environment across the two SIP domains.</span></span> <span data-ttu-id="b18d5-105">Reportez-vous à l’étape 14 dans [consolidation du Cloud pour teams et Skype entreprise](cloud-consolidation.md) pour le contexte dans lequel vous pouvez effectuer cette étape.</span><span class="sxs-lookup"><span data-stu-id="b18d5-105">See step 14 in [Cloud consolidation for Teams and Skype for Business](cloud-consolidation.md) for context in which you might perform this step.</span></span> <span data-ttu-id="b18d5-106">Dans nos exemples, SipDomain1 est AcquiredCompany. <span>com et SipDomain2 sont OriginalCompany. <span>com.</span><span class="sxs-lookup"><span data-stu-id="b18d5-106">In our examples, SipDomain1 is AcquiredCompany.<span>com and SipDomain2 is OriginalCompany.<span>com.</span></span>

<span data-ttu-id="b18d5-107">L’autre nom de l’objet (SAN) du certificat sur tous les serveurs Edge de l’environnement local doit être mis à jour pour inclure tous les domaines SIP existant dans le client pur en ligne (à<span> l’exclusion des onmicrosoft. domaines com), au format «SIP. \<> de domaine».</span><span class="sxs-lookup"><span data-stu-id="b18d5-107">The subject alternate name (SAN) of the certificate on all edge servers in the on-premises environment must be updated to include all SIP domains that exist in the pure online tenant (excluding any onmicrosoft.<span>com domains), in the form “sip.\<domain>”.</span></span>  <span data-ttu-id="b18d5-108">Dans notre exemple, il s’agit de SIP. OriginalCompany. <span>com.</span><span class="sxs-lookup"><span data-stu-id="b18d5-108">In our example, this is sip.OriginalCompany.<span>com.</span></span> <span data-ttu-id="b18d5-109">Cette étape est essentielle avant de migrer des utilisateurs vers le Cloud.</span><span class="sxs-lookup"><span data-stu-id="b18d5-109">This step is critical to do before migrating any users to the cloud.</span></span>

<span data-ttu-id="b18d5-110">**Étapes :**</span><span class="sxs-lookup"><span data-stu-id="b18d5-110">**Steps:**</span></span>

1.  <span data-ttu-id="b18d5-111">Obtenir un nouveau certificat de serveur Edge externe pour le serveur Edge qui dispose de toutes les entrées existantes, ainsi que des entrées supplémentaires dans le SAN pour tous les domaines SIP dans l’environnement Cloud (à l’exception des domaines \*. onmicrosoft.com) au format «SIP. <DomainName>».</span><span class="sxs-lookup"><span data-stu-id="b18d5-111">Obtain a new External Edge certificate for the edge that has all existing entries plus additional entries in the SAN for all SIP domains in the cloud environment (excluding \*.onmicrosoft.com domains) in the form “sip.<DomainName>”.</span></span>
2.  <span data-ttu-id="b18d5-112">Installez le certificat localement sur chaque serveur Edge et affectez-le au service Edge Skype sur chaque service Edge.</span><span class="sxs-lookup"><span data-stu-id="b18d5-112">Install the certificate locally on each edge server and assign it to the Skype Edge service on each of the edge service.</span></span>  <span data-ttu-id="b18d5-113">Pour obtenir la procédure détaillée, voir la section «certificats d’interface Edge externe» dans [Deploy Edge service dans Skype for Business Server 2015](https://technet.microsoft.com/en-us/library/dn951368.aspx).</span><span class="sxs-lookup"><span data-stu-id="b18d5-113">For detailed steps, see the section “External Edge interface certificates” in [Deploy Edge Service in Skype for Business Server 2015](https://technet.microsoft.com/en-us/library/dn951368.aspx).</span></span>
3.  <span data-ttu-id="b18d5-114">Redémarrez le service Edge sur chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="b18d5-114">Restart the Edge service on each of the edge servers.</span></span> <span data-ttu-id="b18d5-115">Vous pouvez effectuer cette opération pour une zone unique avec les commandes PowerShell suivantes:</span><span class="sxs-lookup"><span data-stu-id="b18d5-115">You can do this for a single box with the following PowerShell commands:</span></span>

    ```
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a><span data-ttu-id="b18d5-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b18d5-116">See also</span></span>

[<span data-ttu-id="b18d5-117">Consolidation du Cloud pour teams et Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="b18d5-117">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)