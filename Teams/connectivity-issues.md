---
title: Dépannage des problèmes de connectivité avec le client Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
description: Découvrez comment résoudre les problèmes de connectivité avec le client Microsoft Teams, principalement dûs au pare-feu ou à une connexion proxy.
appliesto:
- Microsoft Teams
ms.openlocfilehash: b95ed6f223b9ec2f5c72a0d387fc1bfd9e693881
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25012136"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="b02f0-103">Dépannage des problèmes de connectivité avec le client Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b02f0-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="b02f0-104">La plupart des problèmes rencontrés avec le client Microsoft Teams peuvent remonter à la connectivité de pare-feu ou proxy.</span><span class="sxs-lookup"><span data-stu-id="b02f0-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="b02f0-105">Vérification que l’URL nécessaires, adresses IP et les ports sont ouverts sur votre pare-feu ou proxy réduit la résolution des problèmes inutiles.</span><span class="sxs-lookup"><span data-stu-id="b02f0-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="b02f0-106">Pour plus d’informations sur les URL et les adresses IP requises pour Microsoft Teams, consultez [Office 365 URL et l’adresse IP](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) prennent en charge de l’article.</span><span class="sxs-lookup"><span data-stu-id="b02f0-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="b02f0-107">Les scénarios suivants nécessitent des URL et les ports à ouvrir dans le pare-feu.</span><span class="sxs-lookup"><span data-stu-id="b02f0-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="b02f0-108">Authentification</span><span class="sxs-lookup"><span data-stu-id="b02f0-108">Authentication</span></span>

-   <span data-ttu-id="b02f0-109">Connectivité client Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b02f0-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="b02f0-110">Collaboration</span><span class="sxs-lookup"><span data-stu-id="b02f0-110">Collaboration</span></span>

-   <span data-ttu-id="b02f0-111">Médias</span><span class="sxs-lookup"><span data-stu-id="b02f0-111">Media</span></span>

-   <span data-ttu-id="b02f0-112">Services partagés</span><span class="sxs-lookup"><span data-stu-id="b02f0-112">Shared Services</span></span>

-   <span data-ttu-id="b02f0-113">Intégration tierce</span><span class="sxs-lookup"><span data-stu-id="b02f0-113">Third Party Integration</span></span>

-   <span data-ttu-id="b02f0-114">Interopérabilité Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="b02f0-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="b02f0-115">Interopérabilité client Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="b02f0-115">Skype for Business Client Interoperability</span></span>
