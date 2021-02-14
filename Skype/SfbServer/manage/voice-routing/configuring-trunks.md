---
title: Configuration des trunks dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Dans le cadre du déploiement Voix Entreprise, vous pouvez configurer une connexion entre un serveur de médiation et un ou plusieurs homologues afin de fournir une connectivité PSTN (réseau téléphonique commuté) pour les clients et périphériques Voix Entreprise de votre organisation.
ms.openlocfilehash: 57b8635d635c0fd0b8c41c95f92af768ff84dfd4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800114"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a><span data-ttu-id="f47ec-103">Configuration des trunks dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="f47ec-103">Configuring trunks in Skype for Business Server</span></span>

<span data-ttu-id="f47ec-104">Dans le cadre d’un déploiement Voix Entreprise, vous pouvez configurer une connexion entre un serveur de médiation et un ou plusieurs des homologues suivants afin de fournir une connectivité PSTN (réseau téléphonique commuté) pour les clients et périphériques Voix Entreprise de votre organisation :</span><span class="sxs-lookup"><span data-stu-id="f47ec-104">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>

- <span data-ttu-id="f47ec-105">Connexion de jonction SIP vers un fournisseur de services de téléphonie Internet</span><span class="sxs-lookup"><span data-stu-id="f47ec-105">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
- <span data-ttu-id="f47ec-106">Passerelle PSTN</span><span class="sxs-lookup"><span data-stu-id="f47ec-106">PSTN gateway</span></span>
- <span data-ttu-id="f47ec-107">Autocommutateur privé (PBX)</span><span class="sxs-lookup"><span data-stu-id="f47ec-107">Private branch exchange (PBX)</span></span>

<span data-ttu-id="f47ec-108">Pour plus d’informations, [voir Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span><span class="sxs-lookup"><span data-stu-id="f47ec-108">For details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f47ec-109">Avant de commencer la configuration des jonctions, vérifiez que la topologie a été créée et que le serveur de médiation et son homologue ont été configurés et associés l’un à l’autre.</span><span class="sxs-lookup"><span data-stu-id="f47ec-109">Before you begin trunk configuration, verify that the topology has been created and that the Mediation Server and its peer have been configured and associated with one another.</span></span> <span data-ttu-id="f47ec-110">Pour plus d’informations, voir Définir une passerelle dans le Générateur de [topologie dans Skype Entreprise Server.](../../deploy/deploy-enterprise-voice/define-a-gateway.md)</span><span class="sxs-lookup"><span data-stu-id="f47ec-110">For details, see [Define a gateway in Topology Builder in Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f47ec-111">Dans le cadre de la configuration de la trunk, vous pouvez activer la fonctionnalité de déviation du média de Skype Entreprise Server, qui permet au média de contourner le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="f47ec-111">As a part of trunk configuration, you can enable the Skype for Business Server media bypass feature, which enables media to bypass the Mediation Server.</span></span> <span data-ttu-id="f47ec-112">Vous pouvez configurer les jonctions sans activer le contournement de média mais nous vous conseillons vivement de l’activer.</span><span class="sxs-lookup"><span data-stu-id="f47ec-112">Trunks can be configured either with or without media bypass enabled, but we strongly recommend that you enable it.</span></span> <span data-ttu-id="f47ec-113">Pour plus d’informations, voir [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="f47ec-113">For details, see [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>
