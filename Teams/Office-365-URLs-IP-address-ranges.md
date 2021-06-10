---
title: Microsoft 365 url Office 365 et des plages d’adresses IP
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Découvrez comment configurer correctement les URL Microsoft 365 ou Office 365 et les plages d’adresses IP, et ignorer le proxy de serveur proxy lorsque c’est possible pour les connexions Microsoft Teams service.
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
ms.openlocfilehash: 9a29984b0b389bacb50a9aa6512a9ccc8bfe07de
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094516"
---
<a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="04dd7-103">Microsoft 365 url Office 365 et des plages d’adresses IP</span><span class="sxs-lookup"><span data-stu-id="04dd7-103">Microsoft 365 and Office 365 URLs and IP address ranges</span></span>
=======================================================

<span data-ttu-id="04dd7-104">Pour obtenir une liste détaillée et à jour des URL, adresses IP, ports et protocoles qui doivent être correctement configurés pour Teams, allez aux URL et [plages](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) d’adresses IP Microsoft 365 et Office 365.</span><span class="sxs-lookup"><span data-stu-id="04dd7-104">Go to [Microsoft 365 and Office 365 URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) for a detailed and up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams.</span></span> <span data-ttu-id="04dd7-105">Microsoft améliore en permanence les services Microsoft 365 et Office 365 et ajoute de nouvelles fonctionnalités, ce que signifie que les ports, URL et adresses IP requis peuvent changer au fil du temps.</span><span class="sxs-lookup"><span data-stu-id="04dd7-105">Microsoft is continuously improving the Microsoft 365 and Office 365 services and adding new functionality, which means the required ports, URLs, and IP addresses may change over time.</span></span> <span data-ttu-id="04dd7-106">Nous vous recommandons de vous [abonner via RSS](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) pour recevoir des notifications lorsque ces informations sont mises à jour ou modifiées.</span><span class="sxs-lookup"><span data-stu-id="04dd7-106">We recommend that you [subscribe via RSS](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) to receive notifications when this information is updated or changed.</span></span>

<span data-ttu-id="04dd7-107">L Teams d’appels et de réunions est basée sur l’infrastructure cloud nouvelle génération utilisée par les utilisateurs de Skype et Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="04dd7-107">The Teams calling and meetings experience is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="04dd7-108">Ces investissements technologiques incluent les services cloud Azure pour le traitement des médias et la signalisation, le codec vidéo H.264, SILK et Service audio codec, la résilience réseau, la télémétrie et les diagnostics de qualité.</span><span class="sxs-lookup"><span data-stu-id="04dd7-108">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span> <span data-ttu-id="04dd7-109">Ainsi, certaines URL et adresses IP requises peuvent être associées à des adresses Skype et Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="04dd7-109">As such, there are URLs and IPs that are required that may be associated with both Skype and Skype for Business.</span></span>

<span data-ttu-id="04dd7-110">Pour toutes les charges Microsoft 365 et Office 365 de travail, la méthode de connexion recommandée pour Teams services contourne le proxy de substitution, si possible.</span><span class="sxs-lookup"><span data-stu-id="04dd7-110">For all Microsoft 365 and Office 365 workloads, the recommended connection method to Teams services is bypassing the forward proxy where possible.</span></span> <span data-ttu-id="04dd7-111">Lorsqu’un serveur proxy se trouve entre un client et les centres de données Office 365, les médias peuvent être forcés sur TCP au lieu d’UDP, ce qui a une incidence sur la qualité des médias.</span><span class="sxs-lookup"><span data-stu-id="04dd7-111">When a proxy server sits between a client and the Office 365 data centers, media might be forced over TCP instead of UDP, which would impact media quality.</span></span> <span data-ttu-id="04dd7-112">Téléchargez des exemples de fichiers PAC proxy qui peuvent être utilisés pour configurer la dérivation pour le trafic à partir de la gestion Microsoft 365 et [Office 365 points de terminaison.](/office365/enterprise/managing-office-365-endpoints)</span><span class="sxs-lookup"><span data-stu-id="04dd7-112">Download sample proxy PAC files that can be used to configure traffic bypass from [Managing Microsoft 365 and Office 365 endpoints](/office365/enterprise/managing-office-365-endpoints).</span></span>

<span data-ttu-id="04dd7-113">Si vos stratégies de réseau et de sécurité nécessitent que le trafic Microsoft 365 ou Office 365 passe par un serveur proxy, assurez-vous que les exigences ci-dessus sont déjà remplies avant de déployer Teams en production.</span><span class="sxs-lookup"><span data-stu-id="04dd7-113">If your networking and security policies require Microsoft 365 or Office 365 traffic to flow through a proxy server, make sure that the above requirements are already met before deploying Teams into production.</span></span> <span data-ttu-id="04dd7-114">Pour plus d’informations, [lisez Serveurs proxy pour Teams ou Skype Entreprise Online.](proxy-servers-for-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="04dd7-114">For more information, read [Proxy Servers for Teams or Skype for Business Online](proxy-servers-for-skype-for-business-online.md).</span></span>