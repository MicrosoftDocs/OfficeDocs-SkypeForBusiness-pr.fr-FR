---
title: Configuration de Trunks dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Dans le cadre d’un déploiement voix entreprise, vous pouvez configurer un Trunk entre un serveur de médiation et un ou plusieurs homologues pour fournir une connectivité PSTN (réseau téléphonique commuté) pour les clients et appareils voix d’entreprise de votre organisation.
ms.openlocfilehash: 41e92f994606ea2153359546d408335d13a21f88
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817014"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a><span data-ttu-id="146a6-103">Configuration de Trunks dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="146a6-103">Configuring trunks in Skype for Business Server</span></span>

<span data-ttu-id="146a6-104">Dans le cadre d’un déploiement voix entreprise, vous pouvez configurer un Trunk entre un serveur de médiation et un ou plusieurs des homologues suivants pour fournir une connectivité PSTN (réseau téléphonique commuté) pour les clients et périphériques vocaux d’entreprise au sein de votre organisation :</span><span class="sxs-lookup"><span data-stu-id="146a6-104">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>

- <span data-ttu-id="146a6-105">Connexion de jonction SIP vers un fournisseur de services de téléphonie Internet</span><span class="sxs-lookup"><span data-stu-id="146a6-105">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
- <span data-ttu-id="146a6-106">Passerelle RTC</span><span class="sxs-lookup"><span data-stu-id="146a6-106">PSTN gateway</span></span>
- <span data-ttu-id="146a6-107">Autocommutateur privé (PBX)</span><span class="sxs-lookup"><span data-stu-id="146a6-107">Private branch exchange (PBX)</span></span>

<span data-ttu-id="146a6-108">Pour plus d’informations, reportez-vous à la rubrique [planification de la connectivité PSTN dans Skype entreprise Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span><span class="sxs-lookup"><span data-stu-id="146a6-108">For details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="146a6-109">Avant de commencer la configuration de Trunk, vérifiez que la topologie a été créée et que le serveur de médiation et son homologue ont été configurés et associés entre eux.</span><span class="sxs-lookup"><span data-stu-id="146a6-109">Before you begin trunk configuration, verify that the topology has been created and that the Mediation Server and its peer have been configured and associated with one another.</span></span> <span data-ttu-id="146a6-110">Pour plus d’informations, reportez-vous à [la section définir une passerelle dans le générateur de topologie de Skype entreprise Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).</span><span class="sxs-lookup"><span data-stu-id="146a6-110">For details, see [Define a gateway in Topology Builder in Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).</span></span>

> [!NOTE]
> <span data-ttu-id="146a6-111">Dans le cadre de la configuration de Trunk, vous pouvez activer la fonctionnalité de contournement de médias de Skype entreprise Server, qui permet aux médias de contourner le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="146a6-111">As a part of trunk configuration, you can enable the Skype for Business Server media bypass feature, which enables media to bypass the Mediation Server.</span></span> <span data-ttu-id="146a6-112">Les Trunks peuvent être configurés avec ou sans Bypass multimédia activé, mais nous vous recommandons vivement de l’activer.</span><span class="sxs-lookup"><span data-stu-id="146a6-112">Trunks can be configured either with or without media bypass enabled, but we strongly recommend that you enable it.</span></span> <span data-ttu-id="146a6-113">Pour plus d’informations, reportez-vous à la rubrique [planification de la dérivation de médias dans Skype entreprise](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="146a6-113">For details, see [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>
