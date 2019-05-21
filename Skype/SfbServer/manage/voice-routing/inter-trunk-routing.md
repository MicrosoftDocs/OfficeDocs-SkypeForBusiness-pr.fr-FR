---
title: Routage inter-Trunk dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Skype entreprise Server fournit une gestion de session de base grâce à la prise en charge du routage intertrunk. '
ms.openlocfilehash: 2c5438f78da78870a5dae8c697d4d30d19a316ce
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274967"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Routage inter-Trunk dans Skype entreprise Server

Skype entreprise Server fournit une gestion de session de base grâce à la prise en charge du routage intertrunk. Cette fonctionnalité permet à Skype entreprise Server de fournir des fonctionnalités de contrôle d’appel aux systèmes de téléphonie en aval. Le routage entre les jonctions peut interconnecter un IP-PBX à une passerelle de réseau de téléphonique commuté (PSTN) pour que les appels d’un téléphone PBX (autocommutateur privé) puissent être acheminés vers la passerelle PSTN et que les appels PSTN entrants puissent être acheminés vers un téléphone PBX. De la même façon, Skype entreprise Server peut interconnecter au moins deux systèmes IP-PBX pour que les appels puissent être placés et reçus entre les téléphones PBX des différents systèmes IP PBX. 


La figure suivante illustre Skype entreprise Server permettant une interconnexion entre une passerelle RTC et un PBX IP.

![Interconnexion entre une passerelle RTC et un PBX IP](../../media/pstn-gateway-ip-pbx.jpg)

La figure suivante illustre Skype entreprise Server connectant deux systèmes PBX IP.

![Skype entreprise Server connectant deux systèmes IP-PGX](../../media/two-ip-pbx-systems.jpg)

