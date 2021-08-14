---
title: Routage inter-Skype Entreprise Server
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
description: 'Skype Entreprise Server gestion des sessions de base via la prise en charge du routage entre les éléments. '
ms.openlocfilehash: 2c2d2dfd1062414de0d11b9e77d7f9f1993a77a14266a8d121b43bfbc12335da
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54351494"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Routage inter-Skype Entreprise Server

Skype Entreprise Server gestion des sessions de base via la prise en charge du routage entre les éléments. Cette fonctionnalité permet aux Skype Entreprise Server de fournir des fonctionnalités de contrôle des appels aux systèmes téléphoniques en aval. Le routage entre les connexions peut interconnecter un SYSTÈME IP-PBX à une passerelle de réseau téléphonique commuté (PSTN) afin que les appels provenant d’un téléphone PBX (autoconnexion privé) soient acheminés vers le réseau téléphonique commuté et que les appels PSTN entrants soient acheminés vers un téléphone PBX. De même, Skype Entreprise Server peut interconnecter au moins deux systèmes IP-PBX afin que les appels soient passé et reçus entre des téléphones PBX à partir des différents systèmes IP-PBX. 


La figure suivante illustre Skype Entreprise Server l’interconnectivité entre une passerelle PSTN et un SYSTÈME IP-PBX.

![Interconnectivité entre une passerelle PSTN et un SYSTÈME IP-PBX](../../media/pstn-gateway-ip-pbx.jpg)

La figure suivante illustre la Skype Entreprise Server deux systèmes IP-PBX.

![Skype Entreprise Server connexion de deux systèmes IP-PGX](../../media/two-ip-pbx-systems.jpg)

