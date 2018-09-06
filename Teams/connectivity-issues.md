---
title: Dépannage des problèmes de connectivité avec le client Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
description: Découvrez comment résoudre les problèmes de connectivité avec le client Microsoft Teams, principalement dûs au pare-feu ou à une connexion proxy.
appliesto:
- Microsoft Teams
ms.openlocfilehash: bc3e7eba6c2aee7786e2a8dd508e6b7f0dcbe329
ms.sourcegitcommit: 33966ebb9ca3d922d47aaa9b9e3a2ddd26c320ca
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/06/2018
ms.locfileid: "23843916"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="ce6d5-103">Dépannage des problèmes de connectivité avec le client Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ce6d5-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="ce6d5-104">La plupart des problèmes rencontrés avec le client Microsoft Teams peuvent remonter à la connectivité de pare-feu ou proxy.</span><span class="sxs-lookup"><span data-stu-id="ce6d5-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="ce6d5-105">Vérification que l’URL nécessaires, adresses IP et les ports sont ouverts sur votre pare-feu ou proxy réduit la résolution des problèmes inutiles.</span><span class="sxs-lookup"><span data-stu-id="ce6d5-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="ce6d5-106">Pour plus d’informations sur les URL et les adresses IP requises pour Microsoft Teams, consultez [Office 365 URL et l’adresse IP](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) prennent en charge de l’article.</span><span class="sxs-lookup"><span data-stu-id="ce6d5-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="ce6d5-107">Les scénarios suivants nécessitent des URL et les ports à ouvrir dans le pare-feu.</span><span class="sxs-lookup"><span data-stu-id="ce6d5-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="ce6d5-108">Authentification</span><span class="sxs-lookup"><span data-stu-id="ce6d5-108">Authentication</span></span>

-   <span data-ttu-id="ce6d5-109">Connectivité client Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ce6d5-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="ce6d5-110">Collaboration</span><span class="sxs-lookup"><span data-stu-id="ce6d5-110">Collaboration</span></span>

-   <span data-ttu-id="ce6d5-111">Médias</span><span class="sxs-lookup"><span data-stu-id="ce6d5-111">Media</span></span>

-   <span data-ttu-id="ce6d5-112">Services partagés</span><span class="sxs-lookup"><span data-stu-id="ce6d5-112">Shared Services</span></span>

-   <span data-ttu-id="ce6d5-113">Intégration tierce</span><span class="sxs-lookup"><span data-stu-id="ce6d5-113">Third Party Integration</span></span>

-   <span data-ttu-id="ce6d5-114">Interopérabilité Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="ce6d5-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="ce6d5-115">Interopérabilité client Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="ce6d5-115">Skype for Business Client Interoperability</span></span>
