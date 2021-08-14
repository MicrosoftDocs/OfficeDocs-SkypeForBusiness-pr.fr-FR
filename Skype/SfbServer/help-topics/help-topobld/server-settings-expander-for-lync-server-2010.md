---
title: Expandeur des paramètres du serveur pour Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: 'Pour modifier les propriétés de cet ordinateur, vous devez :'
ms.openlocfilehash: ee413857ce3b1961887ed48de514c622ba0a6916425899ac387723b734323ef6
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54345741"
---
# <a name="server-settings-expander-for-lync-server-2010"></a>Expandeur des paramètres du serveur pour Lync Server 2010
 
Pour modifier les propriétés de cet ordinateur, vous devez :
  
- Modifiez **le nom de domaine complet (FQDN)** de cet ordinateur. Cette entrée doit correspondre au nom de l’ordinateur tel qu’il est défini dans le système de noms de domaine (DNS) et dans les autres noms du sujet (SAN) ou du nom du sujet (SN) du certificat associé à cet ordinateur.
    
- Vous sélectionnez l’une des sélections suivantes :
    
    **Utilisez toutes les adresses IP configurées**: sélectionnez-la pour utiliser toutes les adresses IP configurées sur l’ordinateur.
    
    > [!IMPORTANT]
    > Si l’ordinateur possède plusieurs adresses IP, vous devez savoir que les services associés à cet ordinateur utiliseront toutes les adresses IP pour tous les services. Si un serveur ou un service d’écoute attend la communication d’une adresse IP et d’un port spécifiques, le service peut ne pas choisir au mieux l’adresse IP à écouter. 
  
    Limiter l’utilisation du service aux **adresses IP sélectionnées**: sélectionnez cette option si vous souhaitez définir des adresses IP spécifiques pour l’adresse **IP** principale que cet ordinateur écoutera pour les communications provenant d’autres ordinateurs et pools dans le déploiement. Définissez **l’adresse IP PSTN** pour l’adresse IP spécifique que l’ordinateur et le service écoutent pour les communications et envoient les communications à la passerelle PSTN ou au SYSTÈME IP-PBX défini.
    

