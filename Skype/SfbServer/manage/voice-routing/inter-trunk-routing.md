---
title: Routage inter-acheminements dans Skype Entreprise Server
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
description: 'Skype Entreprise Server offre une gestion de session de base par le biais de la prise en charge du routage entre les éléments. '
ms.openlocfilehash: d509b4f9de489e65ed8443fd1aad92e24363fb55
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814124"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Routage inter-acheminements dans Skype Entreprise Server

Skype Entreprise Server offre une gestion de session de base par le biais de la prise en charge du routage entre les éléments. Cette fonctionnalité permet à Skype Entreprise Server de fournir des fonctionnalités de contrôle des appels aux systèmes téléphoniques en aval. Le routage entre les connexions peut interconnecter un SYSTÈME IP-PBX à une passerelle de réseau téléphonique commuté (PSTN) afin que les appels provenant d’un téléphone PBX (autoconnexion privé) soient acheminés vers le réseau téléphonique commuté et que les appels PSTN entrants soient acheminés vers un téléphone PBX. De même, Skype Entreprise Server peut interconnecter au moins deux systèmes IP-PBX afin que les appels soient passé et reçus entre des téléphones PBX à partir des différents systèmes IP-PBX. 


La figure suivante illustre Skype Entreprise Server fournissant une interconnectivité entre une passerelle PSTN et un système IP-PBX.

![Interconnectivité entre une passerelle PSTN et un SYSTÈME IP-PBX](../../media/pstn-gateway-ip-pbx.jpg)

La figure suivante illustre la connexion de deux systèmes IP-PBX à Skype Entreprise Server.

![Skype Entreprise Server connectant deux systèmes IP-PGX](../../media/two-ip-pbx-systems.jpg)

