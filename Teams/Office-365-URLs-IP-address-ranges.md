---
title: URL et plages d'adresses IP Office 365
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
description: Découvrez comment configurer des URL et plages d'adresses IP Office 365, contourner le proxy de transfert lorsque cela est possible pour les connexions au service Microsoft Teams, et les conditions requises pour les stratégies de mise en réseau et de sécurité.
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.meetingsettings.network.ports
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e375452e236e38e036a5fe2413ba0848845587ab
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885813"
---
<a name="office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="511eb-103">URL et plages d'adresses IP Office 365</span><span class="sxs-lookup"><span data-stu-id="511eb-103">Office 365 URLs and IP address ranges</span></span>
=====================================

<span data-ttu-id="511eb-104">Accédez à l’article [Plages d'adresses URL et IP d’Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) pour obtenir la liste détaillée et actualisée des URL, adresses IP, ports et protocoles qui doivent être configurés correctement dans Teams.</span><span class="sxs-lookup"><span data-stu-id="511eb-104">Go to [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) for a detailed and up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams.</span></span> <span data-ttu-id="511eb-105">Microsoft améliore en permanence le service Office 365 et ajoute de nouvelles fonctionnalités, ce que signifie que les ports, URL et adresses IP requis peuvent changer au fil du temps.</span><span class="sxs-lookup"><span data-stu-id="511eb-105">Microsoft is continuously improving the Office 365 service and adding new functionality, which means the required ports, URLs, and IP addresses may change over time.</span></span> <span data-ttu-id="511eb-106">Nous vous recommandons de [vous abonner via RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) pour recevoir des notifications lorsque ces informations sont mises à jour ou modifiées.</span><span class="sxs-lookup"><span data-stu-id="511eb-106">We recommend that you [subscribe via RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) to receive notifications when this information is updated or changed.</span></span>

<span data-ttu-id="511eb-107">L'expérience d'appels et de réunions Teams est basée sur l'infrastructure cloud de nouvelle génération, qui est également utilisée par Skype et Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="511eb-107">The Teams calling and meetings experience is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="511eb-108">Ces technologies incluent des services de nuage basée sur Azure pour les médias de traitement et la signalisation, H.264 codec vidéo, soie et signature codec audio, résistance réseau, télémétrie et diagnostics de qualité.</span><span class="sxs-lookup"><span data-stu-id="511eb-108">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span> <span data-ttu-id="511eb-109">Par conséquent, des adresses URL et IP sont requises qui peuvent être associées à Skype et Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="511eb-109">As such, there are URLs and IPs that are required that may be associated with both Skype and Skype for Business.</span></span>

<span data-ttu-id="511eb-110">Pour toutes les charges de travail Office 365, la méthode de connexion aux services Teams recommandée consiste à contourner le proxy de transfert lorsque cela est possible.</span><span class="sxs-lookup"><span data-stu-id="511eb-110">For all Office 365 workloads, the recommended connection method to Teams services is bypassing the forward proxy where possible.</span></span> <span data-ttu-id="511eb-111">Lorsqu’un serveur proxy est situé entre un client et les centres de données Office 365, le média peut être forcé sur TCP au lieu d’UDP, ce qui aurait une incidence sur la qualité du média.</span><span class="sxs-lookup"><span data-stu-id="511eb-111">When a proxy server sits between a client and the Office 365 data centers, media might be forced over TCP instead of UDP, which would impact media quality.</span></span> <span data-ttu-id="511eb-112">Téléchargez les fichiers PAC de modèle de proxy qui peuvent être utilisés pour configurer le contournement du trafic dans [Gestion des points de terminaison Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).</span><span class="sxs-lookup"><span data-stu-id="511eb-112">Download sample proxy PAC files that can be used to configure traffic bypass from [Managing Office 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).</span></span>

<span data-ttu-id="511eb-113">Si vos stratégies de sécurité et de réseau requièrent Office 365 le trafic passe par un serveur proxy, assurez-vous que les conditions ci-dessus sont remplies avant de déployer des équipes en production (passer en revue les [Serveurs Proxy pour les équipes ou Skype pour Business Online](proxy-servers-for-skype-for-business-online.md) Pour obtenir des conseils).</span><span class="sxs-lookup"><span data-stu-id="511eb-113">If your networking and security policies require Office 365 traffic to flow through a proxy server, make sure that the above requirements are already met before deploying Teams into production (review [Proxy Servers for Teams or Skype for Business Online](proxy-servers-for-skype-for-business-online.md) for guidance).</span></span>
