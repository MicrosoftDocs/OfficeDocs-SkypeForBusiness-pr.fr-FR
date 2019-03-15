---
title: Résoudre les problèmes de connectivité avec le client de Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: troubleshooting
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
description: Résoudre les problèmes de connectivité avec le client Microsoft Teams, principalement dû à la connexion de pare-feu ou de proxy et découvrez comment résoudre le problème.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 70255ccbd1c0547c44bb30dee78ffa14d1586705
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/14/2019
ms.locfileid: "30568423"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="544a5-103">Résoudre les problèmes de connectivité avec le client de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="544a5-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="544a5-104">La plupart des problèmes rencontrés avec le client Microsoft Teams peuvent remonter à la connectivité de pare-feu ou proxy.</span><span class="sxs-lookup"><span data-stu-id="544a5-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="544a5-105">Vérification que l’URL nécessaires, adresses IP et les ports sont ouverts sur votre pare-feu ou proxy réduit la résolution des problèmes inutiles.</span><span class="sxs-lookup"><span data-stu-id="544a5-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="544a5-106">Pour plus d’informations sur les URL et les adresses IP requises pour Microsoft Teams, consultez [Office 365 URL et l’adresse IP](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) prennent en charge de l’article.</span><span class="sxs-lookup"><span data-stu-id="544a5-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="544a5-107">Les scénarios suivants nécessitent des URL et les ports à ouvrir dans le pare-feu.</span><span class="sxs-lookup"><span data-stu-id="544a5-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="544a5-108">Authentification</span><span class="sxs-lookup"><span data-stu-id="544a5-108">Authentication</span></span>

-   <span data-ttu-id="544a5-109">Les équipes Microsoft la connectivité des clients</span><span class="sxs-lookup"><span data-stu-id="544a5-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="544a5-110">Collaboration</span><span class="sxs-lookup"><span data-stu-id="544a5-110">Collaboration</span></span>

-   <span data-ttu-id="544a5-111">Media</span><span class="sxs-lookup"><span data-stu-id="544a5-111">Media</span></span>

-   <span data-ttu-id="544a5-112">Services partagés</span><span class="sxs-lookup"><span data-stu-id="544a5-112">Shared Services</span></span>

-   <span data-ttu-id="544a5-113">Intégration de produits tiers</span><span class="sxs-lookup"><span data-stu-id="544a5-113">Third Party Integration</span></span>

-   <span data-ttu-id="544a5-114">Skype pour l’interopérabilité d’entreprise</span><span class="sxs-lookup"><span data-stu-id="544a5-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="544a5-115">Skype pour l’interopérabilité des clients</span><span class="sxs-lookup"><span data-stu-id="544a5-115">Skype for Business Client Interoperability</span></span>
