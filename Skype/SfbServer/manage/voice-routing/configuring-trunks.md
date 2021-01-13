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
# <a name="configuring-trunks-in-skype-for-business-server"></a>Configuration des trunks dans Skype Entreprise Server

Dans le cadre d’un déploiement Voix Entreprise, vous pouvez configurer une connexion entre un serveur de médiation et un ou plusieurs des homologues suivants afin de fournir une connectivité PSTN (réseau téléphonique commuté) pour les clients et périphériques Voix Entreprise de votre organisation :

- Connexion de jonction SIP vers un fournisseur de services de téléphonie Internet
- Passerelle PSTN
- Autocommutateur privé (PBX)

Pour plus d’informations, [voir Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).

> [!IMPORTANT]
> Avant de commencer la configuration des jonctions, vérifiez que la topologie a été créée et que le serveur de médiation et son homologue ont été configurés et associés l’un à l’autre. Pour plus d’informations, voir Définir une passerelle dans le Générateur de [topologie dans Skype Entreprise Server.](../../deploy/deploy-enterprise-voice/define-a-gateway.md)

> [!NOTE]
> Dans le cadre de la configuration de la trunk, vous pouvez activer la fonctionnalité de déviation du média de Skype Entreprise Server, qui permet au média de contourner le serveur de médiation. Vous pouvez configurer les jonctions sans activer le contournement de média mais nous vous conseillons vivement de l’activer. Pour plus d’informations, voir [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).
