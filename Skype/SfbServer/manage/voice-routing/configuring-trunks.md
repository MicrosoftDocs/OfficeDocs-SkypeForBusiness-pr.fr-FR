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
# <a name="configuring-trunks-in-skype-for-business-server"></a>Configuration de Trunks dans Skype entreprise Server

Dans le cadre d’un déploiement voix entreprise, vous pouvez configurer un Trunk entre un serveur de médiation et un ou plusieurs des homologues suivants pour fournir une connectivité PSTN (réseau téléphonique commuté) pour les clients et périphériques vocaux d’entreprise au sein de votre organisation :

- Connexion de jonction SIP vers un fournisseur de services de téléphonie Internet
- Passerelle RTC
- Autocommutateur privé (PBX)

Pour plus d’informations, reportez-vous à la rubrique [planification de la connectivité PSTN dans Skype entreprise Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).

> [!IMPORTANT]
> Avant de commencer la configuration de Trunk, vérifiez que la topologie a été créée et que le serveur de médiation et son homologue ont été configurés et associés entre eux. Pour plus d’informations, reportez-vous à [la section définir une passerelle dans le générateur de topologie de Skype entreprise Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).

> [!NOTE]
> Dans le cadre de la configuration de Trunk, vous pouvez activer la fonctionnalité de contournement de médias de Skype entreprise Server, qui permet aux médias de contourner le serveur de médiation. Les Trunks peuvent être configurés avec ou sans Bypass multimédia activé, mais nous vous recommandons vivement de l’activer. Pour plus d’informations, reportez-vous à la rubrique [planification de la dérivation de médias dans Skype entreprise](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).
