---
title: Dépannage des problèmes de connectivité avec le client Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
description: Découvrez comment résoudre les problèmes de connectivité avec le client Microsoft Teams, principalement dûs au pare-feu ou à une connexion proxy.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5204c745da00535b0838d06a00709ffa31146a3e
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30461659"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="112f7-103">Dépannage des problèmes de connectivité avec le client Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="112f7-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="112f7-104">La plupart des problèmes rencontrés avec le client Microsoft Teams peuvent remonter à la connectivité de pare-feu ou proxy.</span><span class="sxs-lookup"><span data-stu-id="112f7-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="112f7-105">Vérification que l’URL nécessaires, adresses IP et les ports sont ouverts sur votre pare-feu ou proxy réduit la résolution des problèmes inutiles.</span><span class="sxs-lookup"><span data-stu-id="112f7-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="112f7-106">Pour plus d’informations sur les URL et les adresses IP requises pour Microsoft Teams, consultez [Office 365 URL et l’adresse IP](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) prennent en charge de l’article.</span><span class="sxs-lookup"><span data-stu-id="112f7-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="112f7-107">Les scénarios suivants nécessitent des URL et les ports à ouvrir dans le pare-feu.</span><span class="sxs-lookup"><span data-stu-id="112f7-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="112f7-108">Authentification</span><span class="sxs-lookup"><span data-stu-id="112f7-108">Authentication</span></span>

-   <span data-ttu-id="112f7-109">Connectivité client Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="112f7-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="112f7-110">Collaboration</span><span class="sxs-lookup"><span data-stu-id="112f7-110">Collaboration</span></span>

-   <span data-ttu-id="112f7-111">Médias</span><span class="sxs-lookup"><span data-stu-id="112f7-111">Media</span></span>

-   <span data-ttu-id="112f7-112">Services partagés</span><span class="sxs-lookup"><span data-stu-id="112f7-112">Shared Services</span></span>

-   <span data-ttu-id="112f7-113">Intégration tierce</span><span class="sxs-lookup"><span data-stu-id="112f7-113">Third Party Integration</span></span>

-   <span data-ttu-id="112f7-114">Interopérabilité Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="112f7-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="112f7-115">Interopérabilité client Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="112f7-115">Skype for Business Client Interoperability</span></span>
