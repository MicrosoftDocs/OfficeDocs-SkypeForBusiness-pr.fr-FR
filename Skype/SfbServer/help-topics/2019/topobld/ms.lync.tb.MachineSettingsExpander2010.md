---
title: Expanseur des paramètres de serveur pour Lync Server 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: 'Pour modifier les propriétés de cet ordinateur, vous procédez comme suit :'
ms.openlocfilehash: 0e5e595382bb92621c1551158edecf736ff0aa6b
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2018
---
# <a name="server-settings-expander-for-lync-server-2010"></a>Expanseur des paramètres de serveur pour Lync Server 2010
 
Pour modifier les propriétés de cet ordinateur, vous procédez comme suit :
  
- Modifier le **nom de domaine (FQDN) complet** pour cet ordinateur. Cette entrée doit correspondre au nom de l’ordinateur tel qu’il est défini dans le système de nom de domaine (DNS) et dans les noms de sujet (SAN) ou le nom du sujet (SN) du certificat associé à cet ordinateur.
    
- Vous sélectionnez une des options suivantes :
    
    **Utiliser toutes les adresses IP configurées**: sélectionnez cette option pour utiliser toutes les adresses IP sur l’ordinateur.
    
    > [!IMPORTANT]
    > Si l’ordinateur possède plusieurs adresses IP, vous devez être conscient que les services associés à cet ordinateur utilisera toutes les adresses IP pour tous les services. Si un serveur d’écoute ou un service attend la communication d’une adresse IP spécifique et un port, le service peut rendre pas le meilleur choix de l’adresse IP à l’écoute sur. 
  
    **Limitez l’utilisation de service pour les adresses IP sélectionnées**: sélectionnez cette option si vous souhaitez définir des adresses IP spécifiques pour l' **adresse IP principale** qui écoute sur cet ordinateur pour les communications entre les autres ordinateurs et les pools dans le déploiement. Définir **l’adresse IP PSTN** pour l’adresse IP spécifique que l’ordinateur et le service écoute pour les communications et envoyer les communications à la passerelle PSTN ou IP-PBX.
    

