---
title: Configuration de jonctions dans Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Dans le cadre du déploiement d’Enterprise Voice, vous pouvez configurer une jonction entre un serveur de médiation et un ou plusieurs homologues pour fournir un réseau téléphonique commuté (RTC) pour les clients Enterprise Voice et les périphériques de votre organisation.
ms.openlocfilehash: 5e07f0152aac32c4d57962cf619e56777221c955
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883969"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a><span data-ttu-id="262c5-103">Configuration de jonctions dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="262c5-103">Configuring trunks in Skype for Business Server</span></span>

<span data-ttu-id="262c5-104">Dans le cadre du déploiement d’Enterprise Voice, vous pouvez configurer une jonction entre un serveur de médiation et un ou plusieurs des homologues suivantes pour fournir un réseau téléphonique commuté (RTC) pour les clients Enterprise Voice et les périphériques de votre organisation :</span><span class="sxs-lookup"><span data-stu-id="262c5-104">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>

- <span data-ttu-id="262c5-105">Connexion de jonction SIP vers un fournisseur de services de téléphonie Internet</span><span class="sxs-lookup"><span data-stu-id="262c5-105">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
- <span data-ttu-id="262c5-106">Passerelle RTC</span><span class="sxs-lookup"><span data-stu-id="262c5-106">PSTN gateway</span></span>
- <span data-ttu-id="262c5-107">Autocommutateur privé (PBX)</span><span class="sxs-lookup"><span data-stu-id="262c5-107">Private branch exchange (PBX)</span></span>

<span data-ttu-id="262c5-108">Pour plus d’informations, voir [planifier la connectivité PSTN dans Skype pour Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span><span class="sxs-lookup"><span data-stu-id="262c5-108">For details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="262c5-109">Avant de commencer la configuration de jonction, vérifiez que la topologie a été créée et que le serveur de médiation et son homologue ont été configurés et associés à l’autre.</span><span class="sxs-lookup"><span data-stu-id="262c5-109">Before you begin trunk configuration, verify that the topology has been created and that the Mediation Server and its peer have been configured and associated with one another.</span></span> <span data-ttu-id="262c5-110">Pour plus d’informations, voir [définir une passerelle dans le Générateur de topologie dans Skype pour Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).</span><span class="sxs-lookup"><span data-stu-id="262c5-110">For details, see [Define a gateway in Topology Builder in Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).</span></span>

> [!NOTE]
> <span data-ttu-id="262c5-111">Dans le cadre de la configuration de jonction, vous pouvez activer le Skype de fonctionnalité de contournement media Business Server, qui permet de média contourner le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="262c5-111">As a part of trunk configuration, you can enable the Skype for Business Server media bypass feature, which enables media to bypass the Mediation Server.</span></span> <span data-ttu-id="262c5-112">Jonctions peuvent être configurées avec ou sans le contournement de média activé, mais il est vivement recommandé de l’activer.</span><span class="sxs-lookup"><span data-stu-id="262c5-112">Trunks can be configured either with or without media bypass enabled, but we strongly recommend that you enable it.</span></span> <span data-ttu-id="262c5-113">Pour plus d’informations, voir [Plan pour le média de contournement dans Skype pour les entreprises](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="262c5-113">For details, see [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>
