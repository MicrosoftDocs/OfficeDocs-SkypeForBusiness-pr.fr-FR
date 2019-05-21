---
title: Expandeur des paramètres du serveur pour Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: 'Pour modifier les propriétés de cet ordinateur, procédez comme suit:'
ms.openlocfilehash: 28261b3637040acda70218f23101b4337b1f90c3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297609"
---
# <a name="server-settings-expander-for-lync-server-2010"></a>Expandeur des paramètres du serveur pour Lync Server 2010
 
Pour modifier les propriétés de cet ordinateur, procédez comme suit:
  
- Modifiez le **nom de domaine complet (FQDN)** de cet ordinateur. Cette entrée doit correspondre au nom de l’ordinateur tel qu’il est défini dans le système de noms de domaine (DNS), et dans les noms de remplacement de l’objet (SAN) ou le nom d’objet (SN) du certificat associé à cet ordinateur.
    
- Vous pouvez sélectionner l’une des options suivantes:
    
    **Utiliser toutes les adresses IP configurées**: sélectionnez cette option pour utiliser toutes les adresses IP configurées sur l’ordinateur.
    
    > [!IMPORTANT]
    > Si l’ordinateur possède plusieurs adresses IP, vous devez savoir que les services associés à cet ordinateur utiliseront toutes les adresses IP de tous les services. Si un serveur ou un service d’écoute attend une communication d’une adresse IP et d’un port spécifiques, le service n’a peut-être pas la meilleure sélection de l’adresse IP à écouter. 
  
    **Limiter l’utilisation des services aux adresses IP sélectionnées**: sélectionnez cette option si vous voulez définir des adresses IP spécifiques pour l' **adresse IP principale** que cet ordinateur écoute pour la communication à partir d’autres ordinateurs et pools du déploiement. Définissez une **adresse IP PSTN** pour l’adresse IP spécifique que l’ordinateur et le service écouteront pour communiquer et envoyer des communications à la passerelle RTC ou au PBX IP définis.
    

