---
title: Résoudre les problèmes de connectivité avec le client Microsoft Teams
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
f1.keywords:
- NOCSH
description: Résoudre les problèmes de connectivité avec le client Microsoft Teams, principalement causés par le pare-feu ou la connexion proxy, et découvrir comment résoudre ce problème.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a12be097d0609f3631b6761f31350603b283faa2
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825352"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="f7d8a-103">Résoudre les problèmes de connectivité avec le client Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f7d8a-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="f7d8a-104">La plupart des problèmes détectés avec le client Microsoft Teams peuvent être attribués au pare-feu ou à la connectivité du proxy.</span><span class="sxs-lookup"><span data-stu-id="f7d8a-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="f7d8a-105">Vérifier que les URL, les adresses IP et les ports nécessaires sont ouverts dans votre pare-feu ou votre proxy réduit le nombre de dépannages inutiles.</span><span class="sxs-lookup"><span data-stu-id="f7d8a-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="f7d8a-106">Si vous souhaitez en savoir plus sur les URL et les IP requises pour Microsoft Teams, veuillez consulter l'article de support [URL et adresse IP Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span><span class="sxs-lookup"><span data-stu-id="f7d8a-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="f7d8a-107">Les cas suivants nécessitent l'ouverture d'URL et de ports spécifiques dans le pare-feu.</span><span class="sxs-lookup"><span data-stu-id="f7d8a-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="f7d8a-108">Authentification</span><span class="sxs-lookup"><span data-stu-id="f7d8a-108">Authentication</span></span>

-   <span data-ttu-id="f7d8a-109">Connectivité du client Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f7d8a-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="f7d8a-110">Collaboration</span><span class="sxs-lookup"><span data-stu-id="f7d8a-110">Collaboration</span></span>

-   <span data-ttu-id="f7d8a-111">Multimédia</span><span class="sxs-lookup"><span data-stu-id="f7d8a-111">Media</span></span>

-   <span data-ttu-id="f7d8a-112">Services partagés</span><span class="sxs-lookup"><span data-stu-id="f7d8a-112">Shared Services</span></span>

-   <span data-ttu-id="f7d8a-113">Intégration de tiers</span><span class="sxs-lookup"><span data-stu-id="f7d8a-113">Third Party Integration</span></span>

-   <span data-ttu-id="f7d8a-114">Interopérabilité de Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="f7d8a-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="f7d8a-115">Interopérabilité du client Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="f7d8a-115">Skype for Business Client Interoperability</span></span>
