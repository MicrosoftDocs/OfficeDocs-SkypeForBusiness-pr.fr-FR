---
title: 'Skype Entreprise Server : routage inter-acheminements'
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 'Skype Entreprise Server gestion des sessions de base via la prise en charge du routage entre les éléments. '
ms.openlocfilehash: dd63f5f03c46e03f313f9cac42a2432499c216b6
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390996"
---
# <a name="skype-for-business-server-inter-trunk-routing"></a>Skype Entreprise Server : routage inter-acheminements

Skype Entreprise Server gestion des sessions de base via la prise en charge du routage entre les éléments. Cette fonctionnalité permet aux Skype Entreprise Server de fournir des fonctionnalités de contrôle des appels aux systèmes téléphoniques en aval. Le routage entre les connexions peut interconnecter un SYSTÈME IP-PBX à une passerelle de réseau téléphonique commuté (PSTN) afin que les appels provenant d’un téléphone PBX (autoconnexion privé) soient acheminés vers le réseau téléphonique commuté et que les appels PSTN entrants soient acheminés vers un téléphone PBX. De même, Skype Entreprise Server peut interconnecter au moins deux systèmes IP-PBX afin que les appels peuvent être passé et reçus entre des téléphones PBX à partir des différents systèmes IP-PBX. 


La figure suivante illustre Skype Entreprise Server l’interconnectivité entre une passerelle PSTN et un SYSTÈME IP-PBX.

![Interconnectivité entre une passerelle PSTN et un SYSTÈME IP-PBX.](../../media/pstn-gateway-ip-pbx.jpg)

La figure suivante illustre la Skype Entreprise Server deux systèmes IP-PBX.

![Skype Entreprise Server connexion de deux systèmes IP-PGX.](../../media/two-ip-pbx-systems.jpg)

