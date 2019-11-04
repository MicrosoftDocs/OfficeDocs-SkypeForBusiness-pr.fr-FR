---
title: URL et plages d'adresses IP Office 365
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Découvrez comment configurer des URL et plages d'adresses IP Office 365, contourner le proxy de transfert lorsque cela est possible pour les connexions au service Microsoft Teams, et les conditions requises pour les stratégies de mise en réseau et de sécurité.
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.meetingsettings.network.ports
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5fc8d5bc41f7cf7a28140b30dd4a488c05b9b876
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2019
ms.locfileid: "37563870"
---
<a name="office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="f34ad-103">URL et plages d'adresses IP Office 365</span><span class="sxs-lookup"><span data-stu-id="f34ad-103">Office 365 URLs and IP address ranges</span></span>
=====================================

<span data-ttu-id="f34ad-104">Accédez à l’article [Plages d'adresses URL et IP d’Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) pour obtenir la liste détaillée et actualisée des URL, adresses IP, ports et protocoles qui doivent être configurés correctement dans Teams.</span><span class="sxs-lookup"><span data-stu-id="f34ad-104">Go to [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) for a detailed and up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams.</span></span> <span data-ttu-id="f34ad-105">Microsoft améliore en permanence le service Office 365 et ajoute de nouvelles fonctionnalités, ce que signifie que les ports, URL et adresses IP requis peuvent changer au fil du temps.</span><span class="sxs-lookup"><span data-stu-id="f34ad-105">Microsoft is continuously improving the Office 365 service and adding new functionality, which means the required ports, URLs, and IP addresses may change over time.</span></span> <span data-ttu-id="f34ad-106">Nous vous recommandons de [vous abonner via RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) pour recevoir des notifications lorsque ces informations sont mises à jour ou modifiées.</span><span class="sxs-lookup"><span data-stu-id="f34ad-106">We recommend that you [subscribe via RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) to receive notifications when this information is updated or changed.</span></span>

<span data-ttu-id="f34ad-107">L'expérience d'appels et de réunions Teams est basée sur l'infrastructure cloud de nouvelle génération, qui est également utilisée par Skype et Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="f34ad-107">The Teams calling and meetings experience is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="f34ad-108">Ces investissements technologiques incluent les services Cloud Azure pour le traitement et le signalement des contenus multimédias, le codec vidéo H. 264, le codec audio de soie et opus, la résilience réseau, la télémétrie et les diagnostics qualité.</span><span class="sxs-lookup"><span data-stu-id="f34ad-108">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span> <span data-ttu-id="f34ad-109">Par conséquent, des adresses URL et IP sont requises qui peuvent être associées à Skype et Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="f34ad-109">As such, there are URLs and IPs that are required that may be associated with both Skype and Skype for Business.</span></span>

<span data-ttu-id="f34ad-110">Pour toutes les charges de travail Office 365, la méthode de connexion aux services Teams recommandée consiste à contourner le proxy de transfert lorsque cela est possible.</span><span class="sxs-lookup"><span data-stu-id="f34ad-110">For all Office 365 workloads, the recommended connection method to Teams services is bypassing the forward proxy where possible.</span></span> <span data-ttu-id="f34ad-111">Lorsqu’un serveur proxy est situé entre un client et les centres de données Office 365, le média peut être forcé sur TCP au lieu d’UDP, ce qui aurait une incidence sur la qualité du média.</span><span class="sxs-lookup"><span data-stu-id="f34ad-111">When a proxy server sits between a client and the Office 365 data centers, media might be forced over TCP instead of UDP, which would impact media quality.</span></span> <span data-ttu-id="f34ad-112">Téléchargez les fichiers PAC de modèle de proxy qui peuvent être utilisés pour configurer le contournement du trafic dans [Gestion des points de terminaison Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).</span><span class="sxs-lookup"><span data-stu-id="f34ad-112">Download sample proxy PAC files that can be used to configure traffic bypass from [Managing Office 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).</span></span>

<span data-ttu-id="f34ad-113">Si votre réseau et vos stratégies de sécurité nécessitent le trafic d’Office 365 pour circuler par le biais d’un serveur proxy, assurez-vous que les exigences ci-dessus sont déjà satisfaites avant de déployer teams en production (révisez les [serveurs proxy pour teams ou Skype entreprise Online](proxy-servers-for-skype-for-business-online.md) . pour obtenir de l’aide).</span><span class="sxs-lookup"><span data-stu-id="f34ad-113">If your networking and security policies require Office 365 traffic to flow through a proxy server, make sure that the above requirements are already met before deploying Teams into production (review [Proxy Servers for Teams or Skype for Business Online](proxy-servers-for-skype-for-business-online.md) for guidance).</span></span>
