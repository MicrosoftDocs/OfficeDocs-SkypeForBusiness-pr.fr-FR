---
title: Mettre à jour le certificat de serveur edge
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
description: Cette annexe inclut des procédures détaillées pour mettre à jour le certificat de serveur edge dans le cadre de la consolidation de cloud pour les équipes et Skype pour les entreprises.
ms.openlocfilehash: bd7707add0962a827373f1d07de9f8f8f9d3ec7c
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247638"
---
# <a name="update-the-edge-certificate"></a><span data-ttu-id="d3901-103">Mettre à jour le certificat de serveur edge</span><span class="sxs-lookup"><span data-stu-id="d3901-103">Update the edge certificate</span></span>

<span data-ttu-id="d3901-104">Mise à jour le certificat de serveur edge est l’étape clé pour garantir un environnement sur prem avec SipDomain1 permettre participer à un environnement de cloud avec SipDomain2 et garantir un routage correct dans un environnement d’espace d’adressage partagé entre les deux domaines SIP.</span><span class="sxs-lookup"><span data-stu-id="d3901-104">Updating the edge certificate is the key step to ensuring that an on-prem environment with SipDomain1 can join a cloud environment with SipDomain2 and ensure proper routing in a shared address space environment across the two SIP domains.</span></span> <span data-ttu-id="d3901-105">Voir l’étape 14 de [consolidation de Cloud pour les équipes et Skype pour les entreprises](cloud-consolidation.md) pour le contexte dans lequel vous pouvez effectuer cette étape.</span><span class="sxs-lookup"><span data-stu-id="d3901-105">See step 14 in [Cloud consolidation for Teams and Skype for Business](cloud-consolidation.md) for context in which you might perform this step.</span></span> <span data-ttu-id="d3901-106">Dans nos exemples, SipDomain1 est AcquiredCompany. <span>com et SipDomain2 est OriginalCompany. <span>com.</span><span class="sxs-lookup"><span data-stu-id="d3901-106">In our examples, SipDomain1 is AcquiredCompany.<span>com and SipDomain2 is OriginalCompany.<span>com.</span></span>

<span data-ttu-id="d3901-107">L’autre nom du sujet (SAN) du certificat sur tous les serveurs de périphérie dans l’environnement local doit être mis à jour pour inclure tous les domaines SIP qui existent dans le client en ligne pur (à l’exclusion de n’importe quel onmicrosoft.<span> domaines com), sous la forme « sip. \<domaine > ».</span><span class="sxs-lookup"><span data-stu-id="d3901-107">The subject alternate name (SAN) of the certificate on all edge servers in the on-premises environment must be updated to include all SIP domains that exist in the pure online tenant (excluding any onmicrosoft.<span>com domains), in the form “sip.\<domain>”.</span></span>  <span data-ttu-id="d3901-108">Dans notre exemple, il s’agit d’un sip. OriginalCompany. <span>com.</span><span class="sxs-lookup"><span data-stu-id="d3901-108">In our example, this is sip.OriginalCompany.<span>com.</span></span> <span data-ttu-id="d3901-109">Cette étape est essentielle à effectuer avant de migrer des utilisateurs vers le nuage.</span><span class="sxs-lookup"><span data-stu-id="d3901-109">This step is critical to do before migrating any users to the cloud.</span></span>

<span data-ttu-id="d3901-110">**Étapes suivantes :**</span><span class="sxs-lookup"><span data-stu-id="d3901-110">**Steps:**</span></span>

1.  <span data-ttu-id="d3901-111">Obtenir un nouveau certificat de serveur Edge externe du bord qui possède des entrées supplémentaires ainsi que toutes les entrées SAN pour tous les domaines SIP dans l’environnement cloud (à l’exclusion de \*. onmicrosoft.com domaines) sous la forme « sip. <DomainName>».</span><span class="sxs-lookup"><span data-stu-id="d3901-111">Obtain a new External Edge certificate for the edge that has all existing entries plus additional entries in the SAN for all SIP domains in the cloud environment (excluding \*.onmicrosoft.com domains) in the form “sip.<DomainName>”.</span></span>
2.  <span data-ttu-id="d3901-112">Installer le certificat localement sur chaque serveur edge et l’assigner au service Skype Edge sur chacun du service edge.</span><span class="sxs-lookup"><span data-stu-id="d3901-112">Install the certificate locally on each edge server and assign it to the Skype Edge service on each of the edge service.</span></span>  <span data-ttu-id="d3901-113">Pour obtenir la procédure détaillée, voir la section « Certificats d’interface externe Edge » dans [Déployer le Service Edge dans Skype pour Business Server 2015](https://technet.microsoft.com/en-us/library/dn951368.aspx).</span><span class="sxs-lookup"><span data-stu-id="d3901-113">For detailed steps, see the section “External Edge interface certificates” in [Deploy Edge Service in Skype for Business Server 2015](https://technet.microsoft.com/en-us/library/dn951368.aspx).</span></span>
3.  <span data-ttu-id="d3901-114">Redémarrez le service Edge sur chacun des serveurs de périphérie.</span><span class="sxs-lookup"><span data-stu-id="d3901-114">Restart the Edge service on each of the edge servers.</span></span> <span data-ttu-id="d3901-115">Vous pouvez le faire pour une seule boîte avec les commandes PowerShell suivantes :</span><span class="sxs-lookup"><span data-stu-id="d3901-115">You can do this for a single box with the following PowerShell commands:</span></span>

    ```
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a><span data-ttu-id="d3901-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d3901-116">See also</span></span>

[<span data-ttu-id="d3901-117">Consolidation de cloud pour les équipes et Skype pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="d3901-117">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)