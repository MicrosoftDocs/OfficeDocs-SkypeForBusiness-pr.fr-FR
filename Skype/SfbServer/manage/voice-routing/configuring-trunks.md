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
# <a name="configuring-trunks-in-skype-for-business-server"></a>Configuration de jonctions dans Skype pour Business Server

Dans le cadre du déploiement d’Enterprise Voice, vous pouvez configurer une jonction entre un serveur de médiation et un ou plusieurs des homologues suivantes pour fournir un réseau téléphonique commuté (RTC) pour les clients Enterprise Voice et les périphériques de votre organisation :

- Connexion de jonction SIP vers un fournisseur de services de téléphonie Internet
- Passerelle RTC
- Autocommutateur privé (PBX)

Pour plus d’informations, voir [planifier la connectivité PSTN dans Skype pour Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).

> [!IMPORTANT]
> Avant de commencer la configuration de jonction, vérifiez que la topologie a été créée et que le serveur de médiation et son homologue ont été configurés et associés à l’autre. Pour plus d’informations, voir [définir une passerelle dans le Générateur de topologie dans Skype pour Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).

> [!NOTE]
> Dans le cadre de la configuration de jonction, vous pouvez activer le Skype de fonctionnalité de contournement media Business Server, qui permet de média contourner le serveur de médiation. Jonctions peuvent être configurées avec ou sans le contournement de média activé, mais il est vivement recommandé de l’activer. Pour plus d’informations, voir [Plan pour le média de contournement dans Skype pour les entreprises](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).
