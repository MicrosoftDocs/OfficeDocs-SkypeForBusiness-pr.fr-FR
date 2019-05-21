---
title: Configuration de Trunks dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Dans le cadre d’un déploiement voix entreprise, vous pouvez configurer un Trunk entre un serveur de médiation et un ou plusieurs homologues pour fournir une connectivité PSTN (réseau téléphonique commuté) pour les clients et appareils voix d’entreprise de votre organisation.
ms.openlocfilehash: c350723720dccee069a28a4d9aa2c40517f6d1bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275002"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a><span data-ttu-id="390aa-103">Configuration de Trunks dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="390aa-103">Configuring trunks in Skype for Business Server</span></span>

<span data-ttu-id="390aa-104">Dans le cadre d’un déploiement voix entreprise, vous pouvez configurer un Trunk entre un serveur de médiation et un ou plusieurs des homologues suivants pour fournir une connectivité PSTN (réseau téléphonique commuté) pour les clients et périphériques vocaux d’entreprise au sein de votre organisation:</span><span class="sxs-lookup"><span data-stu-id="390aa-104">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>

- <span data-ttu-id="390aa-105">Connexion de jonction SIP vers un fournisseur de services de téléphonie Internet</span><span class="sxs-lookup"><span data-stu-id="390aa-105">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
- <span data-ttu-id="390aa-106">Passerelle RTC</span><span class="sxs-lookup"><span data-stu-id="390aa-106">PSTN gateway</span></span>
- <span data-ttu-id="390aa-107">Autocommutateur privé (PBX)</span><span class="sxs-lookup"><span data-stu-id="390aa-107">Private branch exchange (PBX)</span></span>

<span data-ttu-id="390aa-108">Pour plus d’informations, reportez-vous à la rubrique [planification de la connectivité PSTN dans Skype entreprise Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span><span class="sxs-lookup"><span data-stu-id="390aa-108">For details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="390aa-109">Avant de commencer la configuration de Trunk, vérifiez que la topologie a été créée et que le serveur de médiation et son homologue ont été configurés et associés entre eux.</span><span class="sxs-lookup"><span data-stu-id="390aa-109">Before you begin trunk configuration, verify that the topology has been created and that the Mediation Server and its peer have been configured and associated with one another.</span></span> <span data-ttu-id="390aa-110">Pour plus d’informations, reportez-vous à [la section définir une passerelle dans le générateur de topologie de Skype entreprise Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).</span><span class="sxs-lookup"><span data-stu-id="390aa-110">For details, see [Define a gateway in Topology Builder in Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).</span></span>

> [!NOTE]
> <span data-ttu-id="390aa-111">Dans le cadre de la configuration de Trunk, vous pouvez activer la fonctionnalité de contournement de médias de Skype entreprise Server, qui permet aux médias de contourner le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="390aa-111">As a part of trunk configuration, you can enable the Skype for Business Server media bypass feature, which enables media to bypass the Mediation Server.</span></span> <span data-ttu-id="390aa-112">Les Trunks peuvent être configurés avec ou sans Bypass multimédia activé, mais nous vous recommandons vivement de l’activer.</span><span class="sxs-lookup"><span data-stu-id="390aa-112">Trunks can be configured either with or without media bypass enabled, but we strongly recommend that you enable it.</span></span> <span data-ttu-id="390aa-113">Pour plus d’informations, reportez-vous à la rubrique [planification de la dérivation de médias dans Skype entreprise](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="390aa-113">For details, see [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>
