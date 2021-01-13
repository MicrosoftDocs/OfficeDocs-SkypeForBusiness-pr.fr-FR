---
title: Routage inter-acheminements dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: Découvrez comment Skype Entreprise Server Voix Entreprise prend en charge le routage inter-acheminements.
ms.openlocfilehash: fc03f0df530be12ad1d08148850c11d8f92a2791
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825595"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Routage inter-acheminements dans Skype Entreprise Server
 
Découvrez comment Skype Entreprise Server Voix Entreprise prend en charge le routage inter-acheminements.
  
Skype Entreprise Server offre une gestion de session de base par le biais de la prise en charge du routage entre les éléments. Cela permet à Skype Entreprise Server de fournir des fonctionnalités de contrôle des appels aux systèmes téléphoniques en aval. Le routage entre les connexions peut interconnecter un SYSTÈME IP-PBX à une passerelle de réseau téléphonique commuté (PSTN) afin que les appels provenant d’un téléphone PBX (autoconnexion privé) soient acheminés vers le réseau téléphonique commuté et que les appels PSTN entrants soient acheminés vers un téléphone PBX. De même, Skype Entreprise Server peut interconnecter au moins deux systèmes IP-PBX afin que les appels soient passé et reçus entre des téléphones PBX à partir des différents systèmes IP-PBX. 
  
La figure suivante illustre Skype Entreprise Server fournissant une interconnectivité entre une passerelle PSTN et un système IP-PBX.
  
![Diagramme Lync Server connectant la passerelle PSTN/IP-PBX](../../media/inter_trunk01.jpg)
  
La figure suivante illustre la connexion de deux systèmes IP-PBX à Skype Entreprise Server.
  
![Diagramme Lync Server interconnectant les systèmes IP-PAX](../../media/inter_trunk02.jpg)
  

