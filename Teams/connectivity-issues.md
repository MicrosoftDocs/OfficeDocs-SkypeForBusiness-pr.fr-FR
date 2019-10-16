---
title: Résoudre les problèmes de connectivité avec le client de Microsoft Teams
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Résoudre les problèmes de connectivité avec le client Microsoft Teams, principalement causés par le pare-feu ou la connexion proxy, et découvrir comment résoudre ce problème.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7779e46fc0a1c8a282c5cde38ecac6389824a268
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516460"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="4ec8d-103">Résoudre les problèmes de connectivité avec le client de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4ec8d-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="4ec8d-104">La plupart des problèmes détectés avec le client Microsoft teams peuvent être retrouvés dans la connectivité de pare-feu ou de proxy.</span><span class="sxs-lookup"><span data-stu-id="4ec8d-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="4ec8d-105">La vérification de l’ouverture des URL nécessaires, des adresses IP et des ports par le pare-feu ou le serveur proxy permet de réduire les problèmes inutiles.</span><span class="sxs-lookup"><span data-stu-id="4ec8d-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="4ec8d-106">Pour obtenir des informations spécifiques sur les URL et IPs nécessaires à Microsoft Teams, voir l’article [URL et adresse IP d’Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) .</span><span class="sxs-lookup"><span data-stu-id="4ec8d-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="4ec8d-107">Les scénarios suivants nécessitent l’ouverture d’URL et de ports spécifiques dans le pare-feu.</span><span class="sxs-lookup"><span data-stu-id="4ec8d-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="4ec8d-108">Authentification</span><span class="sxs-lookup"><span data-stu-id="4ec8d-108">Authentication</span></span>

-   <span data-ttu-id="4ec8d-109">Connectivité du client Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="4ec8d-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="4ec8d-110">Équipe</span><span class="sxs-lookup"><span data-stu-id="4ec8d-110">Collaboration</span></span>

-   <span data-ttu-id="4ec8d-111">Media</span><span class="sxs-lookup"><span data-stu-id="4ec8d-111">Media</span></span>

-   <span data-ttu-id="4ec8d-112">Services partagés</span><span class="sxs-lookup"><span data-stu-id="4ec8d-112">Shared Services</span></span>

-   <span data-ttu-id="4ec8d-113">Intégration d’une tierce partie</span><span class="sxs-lookup"><span data-stu-id="4ec8d-113">Third Party Integration</span></span>

-   <span data-ttu-id="4ec8d-114">Interopérabilité entre Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="4ec8d-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="4ec8d-115">Interopérabilité du client Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="4ec8d-115">Skype for Business Client Interoperability</span></span>
