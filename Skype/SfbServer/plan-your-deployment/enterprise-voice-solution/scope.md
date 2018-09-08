---
title: Définir l’étendue du déploiement E9-1-1 de Skype pour Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: Décisions nécessaires pour planifier un déploiement E9-1-1 dans Skype Business Server Enterprise Voice.
ms.openlocfilehash: 01b6b1656826977444928583ff08e8cb23b2982d
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23886288"
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server"></a><span data-ttu-id="94906-103">Définir l’étendue du déploiement E9-1-1 de Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="94906-103">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>

<span data-ttu-id="94906-104">Décisions nécessaires pour planifier un déploiement E9-1-1 dans Skype Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="94906-104">Decisions necessary for planning an E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="94906-105">Avant de configurer Skype pour les entreprises pour E9-1-1, vous devez planifier votre déploiement E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="94906-105">Before you configure Skype for Business for E9-1-1, you need to plan your E9-1-1 deployment.</span></span> <span data-ttu-id="94906-106">Voici certaines des questions que vous pouvez vous poser :</span><span class="sxs-lookup"><span data-stu-id="94906-106">Some of the questions to consider include:</span></span>

 <span data-ttu-id="94906-107">**Quelles sont la stratégie de votre organisation et les obligations légales concernant E9-1-1 ?**</span><span class="sxs-lookup"><span data-stu-id="94906-107">**What are your organization's policy and legal obligations with regard to E9-1-1?**</span></span>

 <span data-ttu-id="94906-108">Les obligations légales en matière d’E9-1-1 pour les PBX (appelés aussi systèmes téléphoniques multilignes, ou MLTS (Multi-line Telephone Systems) dans le langage E9-1-1) diffèrent d’un État à l’autre.</span><span class="sxs-lookup"><span data-stu-id="94906-108">E9-1-1 legal requirements for PBXs (called Multi-line Telephone Systems, or MLTS, in E9-1-1 parlance) differ from state to state.</span></span> <span data-ttu-id="94906-109">Vous devez consulter votre équipe juridique de comprendre les obligations applicables à votre déploiement de Skype pour l’entreprise dans vos sites pertinents.</span><span class="sxs-lookup"><span data-stu-id="94906-109">You should consult with your legal team to understand the obligations that may apply to your deployment of Skype for Business in your relevant geographies.</span></span>

 <span data-ttu-id="94906-110">**Quels secteurs de votre entreprise doivent être activés pour E9-1-1 ?**</span><span class="sxs-lookup"><span data-stu-id="94906-110">**What areas within your enterprise need to be enabled for E9-1-1?**</span></span>

 <span data-ttu-id="94906-p103">Vous pouvez activer E9-1-1 à des emplacements spécifiques ou dans toute l’entreprise. Par exemple, votre utilisation d’E9-1-1 peut varier selon les États ou pays/régions dans lesquels les bureaux de votre entreprise se trouvent, ou bien vous pouvez exclure les sites se trouvant en dehors des États-Unis.</span><span class="sxs-lookup"><span data-stu-id="94906-p103">You can enable E9-1-1 for the entire enterprise or for selected locations. For example, you may have varying E9-1-1 requirements for offices in different states, or you may want to exclude sites outside the U.S.</span></span>

 <span data-ttu-id="94906-113">**Comment allez-vous déployer E9-1-1 sur des sites de succursale ?**</span><span class="sxs-lookup"><span data-stu-id="94906-113">**How will you deploy E9-1-1 to branch sites?**</span></span>

 <span data-ttu-id="94906-114">La résistance des communications vocales est un concept qu’il est important de comprendre si vous déployez E9-1-1 sur un site de succursale.</span><span class="sxs-lookup"><span data-stu-id="94906-114">Voice resiliency is an important concept to understand when deploying E9-1-1 at a branch site.</span></span> <span data-ttu-id="94906-115">Si vous avez centralisé jonctions SIP E-9-1-1 et une panne de réseau étendu, clients connexion pas peut-être d’obtention d’un emplacement de service d’informations sur l’emplacement ou pour se connecter pour le fournisseur de services d’urgence.</span><span class="sxs-lookup"><span data-stu-id="94906-115">If you have centralized E-9-1-1 SIP trunks and a WAN outage occurs, clients signing in may not be able to obtain a location from Location Information service or to connect to the emergency services service provider.</span></span> <span data-ttu-id="94906-116">Skype pour les entreprises fournit plusieurs stratégies de gestion de la résilience vocale dans les succursales, y compris : ayant des réseaux de données résistantes, le déploiement d’une jonction SIP à chaque branche ou diffuser les appels d’urgence vers la passerelle locale pendant les pannes.</span><span class="sxs-lookup"><span data-stu-id="94906-116">Skype for Business provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing emergency calls out to the local gateway during outages.</span></span> <span data-ttu-id="94906-117">Pour plus d’informations, voir [Planning for Branch-Site Voice Resiliency](https://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx).</span><span class="sxs-lookup"><span data-stu-id="94906-117">For details, see [Planning for Branch-Site Voice Resiliency](https://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx).</span></span>

 <span data-ttu-id="94906-118">**Allez-vous activer E9-1-1 pour les utilisateurs travaillant en dehors du réseau ?**</span><span class="sxs-lookup"><span data-stu-id="94906-118">**Will you enable E9-1-1 for users working outside the network?**</span></span>

 <span data-ttu-id="94906-119">Acquisition de l’emplacement automatique est disponible uniquement pour les clients situés à l’intérieur du réseau de l’organisation, afin que votre organisation doit décider si elle prendra en charge les appels E9-1-1 à partir de Skype pour les clients professionnels lors hors site.</span><span class="sxs-lookup"><span data-stu-id="94906-119">Automatic location acquisition is available only for clients located inside the organization's network, so your organization needs to decide whether it will support E9-1-1 calls made from Skype for Business clients while off-premises.</span></span> <span data-ttu-id="94906-120">Par exemple, allez-vous autoriser les utilisateurs à passer des appels d’urgence quand ils travaillent de chez eux ou chez un client ?</span><span class="sxs-lookup"><span data-stu-id="94906-120">For example, will you enable users to place emergency calls if they are working from home or from a customer site?</span></span> <span data-ttu-id="94906-121">Si un client se trouve en dehors du réseau d’entreprise, il peut être configuré de sorte à inviter l’utilisateur à indiquer son emplacement.</span><span class="sxs-lookup"><span data-stu-id="94906-121">If a client is located outside the enterprise network, the client can be configured to prompt the user for a location.</span></span> <span data-ttu-id="94906-122">Cependant, les emplacements fournis par l’utilisateur ne peuvent pas être prévalidés par rapport au guide MSAG (Master Street Address Guide), le répartiteur du fournisseur de services d’urgence devra donc confirmer verbalement avec l’appelant la validité de son emplacement avant d’acheminer l’appel vers le centre téléphonique de sécurité publique (Public Safety Answering Point ou PSAP).</span><span class="sxs-lookup"><span data-stu-id="94906-122">However, because these user-provided locations cannot be prevalidated against the Master Street Address Guide (MSAG), the emergency services service provider dispatcher will need to confirm the validity of the location verbally with the caller before routing the call to the Public Safety Answering Point (PSAP).</span></span>

> [!NOTE]
> <span data-ttu-id="94906-123">Skype pour les clients d’entreprise d’utilisateurs qui se connectent au réseau de votre organisation à l’aide de VPN peut prendre les informations d’adresse IP internes, mais étant donné que ces adresses ne peut pas être utilisés pour identifier l’emplacement réel de l’utilisateur, il est essentiel que les sous-réseaux de réseau privé virtuel sont exclus à partir du service informations d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="94906-123">Skype for Business clients of users who connect to your organization's network by using VPN can pick up internal IP address information, but because these addresses cannot be used to identify the user's actual location, it is essential that VPN subnets are excluded from the Location Information service.</span></span>

 <span data-ttu-id="94906-124">**Voulez-vous que les appels d’urgence soient acheminés vers des sites en dehors des États-Unis ?**</span><span class="sxs-lookup"><span data-stu-id="94906-124">**Do you want to provide emergency call routing to sites outside the U.S.?**</span></span>

 <span data-ttu-id="94906-p106">Vous voudrez peut-être que des zones de votre entreprise bénéficient du routage des appels d’urgence alors qu’elles ne disposent pas d’un fournisseur de services d’urgence (par exemple, des sites à l’étranger). Pour ce faire, créez un site, puis affectez des stratégies de voix aux sites qui utilisent le réseau RTC pour acheminer l’appel via une passerelle RTC locale.</span><span class="sxs-lookup"><span data-stu-id="94906-p106">You may want to provide emergency routing to areas of your company not served by an emergency services service provider (for example, international locations). To do this, create a new site, and then assign voice policies to the sites that refer to a PSTN usage that routes the call through the local PSTN gateway.</span></span>


