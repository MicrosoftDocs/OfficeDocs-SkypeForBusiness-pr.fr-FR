---
title: URL et plages d’adresses IP de Microsoft 365 et Office 365
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Apprenez à configurer correctement les URL et plages d’adresses IP de Microsoft 365 ou d’Office 365 et à ignorer le proxy de transfert dans la mesure du possible pour les connexions au service Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.network.ports
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 30736a347f447d265059de1a26ded5ef690e53dc
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44665688"
---
<a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="60b5d-103">URL et plages d’adresses IP de Microsoft 365 et Office 365</span><span class="sxs-lookup"><span data-stu-id="60b5d-103">Microsoft 365 and Office 365 URLs and IP address ranges</span></span>
=======================================================

<span data-ttu-id="60b5d-104">Accédez aux [URL et plages d’adresses IP de Microsoft 365 et Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) pour obtenir une liste détaillée et à jour des URL, adresses IP, ports et protocoles qui doivent être correctement configurés pour les équipes.</span><span class="sxs-lookup"><span data-stu-id="60b5d-104">Go to [Microsoft 365 and Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) for a detailed and up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams.</span></span> <span data-ttu-id="60b5d-105">Microsoft améliore continuellement les services Microsoft 365 et Office 365 et ajoute de nouvelles fonctionnalités, ce qui signifie que les ports, URL et adresses IP requis risquent de changer dans le temps.</span><span class="sxs-lookup"><span data-stu-id="60b5d-105">Microsoft is continuously improving the Microsoft 365 and Office 365 services and adding new functionality, which means the required ports, URLs, and IP addresses may change over time.</span></span> <span data-ttu-id="60b5d-106">Nous vous recommandons de [vous abonner via RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) pour recevoir des notifications lorsque ces informations sont mises à jour ou modifiées.</span><span class="sxs-lookup"><span data-stu-id="60b5d-106">We recommend that you [subscribe via RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) to receive notifications when this information is updated or changed.</span></span>

<span data-ttu-id="60b5d-107">L'expérience d'appels et de réunions Teams est basée sur l'infrastructure cloud de nouvelle génération, qui est également utilisée par Skype et Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="60b5d-107">The Teams calling and meetings experience is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="60b5d-108">Ces investissements technologiques incluent les services Cloud Azure pour le traitement et le signalement des contenus multimédias, le codec vidéo H. 264, le codec audio de soie et opus, la résilience réseau, la télémétrie et les diagnostics qualité.</span><span class="sxs-lookup"><span data-stu-id="60b5d-108">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span> <span data-ttu-id="60b5d-109">Par conséquent, des adresses URL et IP sont requises qui peuvent être associées à Skype et Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="60b5d-109">As such, there are URLs and IPs that are required that may be associated with both Skype and Skype for Business.</span></span>

<span data-ttu-id="60b5d-110">Pour toutes les charges de travail Microsoft 365 et Office 365, la méthode de connexion recommandée aux services d’équipe ignore le proxy de transfert, dans la mesure du possible.</span><span class="sxs-lookup"><span data-stu-id="60b5d-110">For all Microsoft 365 and Office 365 workloads, the recommended connection method to Teams services is bypassing the forward proxy where possible.</span></span> <span data-ttu-id="60b5d-111">Lorsqu’un serveur proxy est situé entre un client et les centres de données Office 365, le média peut être forcé sur TCP au lieu d’UDP, ce qui aurait une incidence sur la qualité du média.</span><span class="sxs-lookup"><span data-stu-id="60b5d-111">When a proxy server sits between a client and the Office 365 data centers, media might be forced over TCP instead of UDP, which would impact media quality.</span></span> <span data-ttu-id="60b5d-112">Téléchargez des exemples de fichiers PAC de proxy qui peuvent être utilisés pour configurer le contournement du trafic à partir de la [gestion des points de terminaison Microsoft 365 et Office 365](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints).</span><span class="sxs-lookup"><span data-stu-id="60b5d-112">Download sample proxy PAC files that can be used to configure traffic bypass from [Managing Microsoft 365 and Office 365 endpoints](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints).</span></span>

<span data-ttu-id="60b5d-113">Si votre réseau et vos stratégies de sécurité nécessitent le trafic Microsoft 365 ou Office 365 pour passer par le biais d’un serveur proxy, assurez-vous que les exigences ci-dessus sont déjà satisfaites avant de déployer teams en production.</span><span class="sxs-lookup"><span data-stu-id="60b5d-113">If your networking and security policies require Microsoft 365 or Office 365 traffic to flow through a proxy server, make sure that the above requirements are already met before deploying Teams into production.</span></span> <span data-ttu-id="60b5d-114">Pour plus d’informations, voir [serveurs proxy pour teams ou Skype entreprise Online](proxy-servers-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="60b5d-114">For more information, read [Proxy Servers for Teams or Skype for Business Online](proxy-servers-for-skype-for-business-online.md).</span></span>
