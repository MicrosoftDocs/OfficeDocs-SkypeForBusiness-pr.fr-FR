---
title: Configuration des trunks dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Dans le cadre du déploiement Voix Entreprise, vous pouvez configurer une connexion entre un serveur de médiation et un ou plusieurs homologues afin de fournir une connectivité PSTN (réseau téléphonique commuté) pour les clients et périphériques Voix Entreprise de votre organisation.
ms.openlocfilehash: 528dc8accbb2165bb86f3de9f10b3141dea01143
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60739160"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a>Configuration des trunks dans Skype Entreprise Server

Dans le cadre du déploiement Voix Entreprise, vous pouvez configurer une connexion entre un serveur de médiation et un ou plusieurs des homologues suivants pour fournir une connectivité PSTN (réseau téléphonique commuté) pour les clients et périphériques Voix Entreprise de votre organisation :

- Connexion de jonction SIP vers un fournisseur de services de téléphonie Internet
- Passerelle PSTN
- Autocommutateur privé (PBX)

Pour plus d’informations, [voir Planifier la connectivité PSTN dans Skype Entreprise Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).

> [!IMPORTANT]
> Avant de commencer la configuration des jonctions, vérifiez que la topologie a été créée et que le serveur de médiation et son homologue ont été configurés et associés l’un à l’autre. Pour plus d’informations, voir Définir une passerelle dans le Générateur de [topologies dans Skype Entreprise Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).

> [!NOTE]
> Dans le cadre de la configuration de la Skype Entreprise Server, vous pouvez activer la fonctionnalité de déviation du Skype Entreprise Server multimédia, qui permet au média de contourner le serveur de médiation. Vous pouvez configurer les jonctions sans activer le contournement de média mais nous vous conseillons vivement de l’activer. Pour plus d’informations, [voir Plan for media bypass in Skype Entreprise](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).
