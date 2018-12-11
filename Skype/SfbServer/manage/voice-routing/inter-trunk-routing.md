---
title: Routage entre les jonctions dans Skype pour Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Skype pour Business Server assure la gestion de session de base par le biais de la prise en charge de routage d’inter-jonctions. '
ms.openlocfilehash: 66ee1f0cb9e37587d3c581b895528e27e7fad6c0
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222813"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Routage entre les jonctions dans Skype pour Business Server

Skype pour Business Server assure la gestion de session de base par le biais de la prise en charge de routage d’inter-jonctions. Cette fonctionnalité permet de Skype pour Business Server fournir des fonctionnalités de contrôle d’appel aux systèmes de téléphonie en aval. Le routage entre les jonctions peut interconnecter un IP-PBX à une passerelle de réseau de téléphonique commuté (PSTN) pour que les appels d’un téléphone PBX (autocommutateur privé) puissent être acheminés vers la passerelle PSTN et que les appels PSTN entrants puissent être acheminés vers un téléphone PBX. De même, Skype pour Business Server peut interconnect deux ou plusieurs systèmes IP-PBX afin que les appels peuvent être placés et reçus entre les téléphones PBX à partir de différents systèmes IP-PBX. 


La figure suivante illustre Skype pour Business Server fournissant une interconnectivité entre une passerelle PSTN et un IP-PBX.

![Interconnectivité entre une passerelle PSTN et un IP-PBX](../../media/pstn-gateway-ip-pbx.jpg)

La figure suivante illustre Skype pour Business Server connectent deux systèmes IP-PBX.

![Skype pour Business Server connectent deux systèmes IP-PGX](../../media/two-ip-pbx-systems.jpg)

