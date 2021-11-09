---
title: À propos du routage inter-Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: Découvrez comment Skype Entreprise Server Voix Entreprise prend en charge le routage inter-acheminements.
ms.openlocfilehash: 16a67af73db89f884f797c24123b984d3eb87789
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60855411"
---
# <a name="about-inter-trunk-routing-in-skype-for-business-server"></a>À propos du routage inter-Skype Entreprise Server
 
Découvrez comment Skype Entreprise Server Voix Entreprise prend en charge le routage inter-acheminements.
  
Skype Entreprise Server gestion des sessions de base via la prise en charge du routage entre les éléments. Cela permet aux Skype Entreprise Server de fournir des fonctionnalités de contrôle des appels aux systèmes téléphoniques en aval. Le routage entre les connexions peut interconnecter un SYSTÈME IP-PBX à une passerelle de réseau téléphonique commuté (PSTN) afin que les appels provenant d’un téléphone PBX (autoconnexion privé) soient acheminés vers le réseau téléphonique commuté et que les appels PSTN entrants soient acheminés vers un téléphone PBX. De même, Skype Entreprise Server peut interconnecter au moins deux systèmes IP-PBX afin que les appels peuvent être passé et reçus entre des téléphones PBX à partir des différents systèmes IP-PBX. 
  
La figure suivante illustre Skype Entreprise Server l’interconnectivité entre une passerelle PSTN et un SYSTÈME IP-PBX.
  
![Diagramme Lync Server connectant la passerelle PSTN/IP-PBX.](../../media/inter_trunk01.jpg)
  
La figure suivante illustre la Skype Entreprise Server deux systèmes IP-PBX.
  
![Diagramme Lync Server interconnectant les systèmes IP-PAX.](../../media/inter_trunk02.jpg)
  

