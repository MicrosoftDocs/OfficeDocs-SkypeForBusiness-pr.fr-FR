---
title: Expandeur des paramètres du serveur pour Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Pour modifier les propriétés de cet ordinateur, procédez comme suit :'
ms.openlocfilehash: c0eb39a516cbcce18940abe7936747fc18db9761
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215695"
---
# <a name="server-settings-expander-for-lync-server-2010"></a>Expandeur des paramètres du serveur pour Lync Server 2010
 
Pour modifier les propriétés de cet ordinateur, procédez comme suit :
  
- Modifiez le **nom de domaine complet (FQDN)** de cet ordinateur. Cette entrée doit correspondre au nom de l’ordinateur, tel qu’il est défini dans le DNS (Domain Name System), et dans les autres noms du sujet (SAN) ou le nom de l’objet (SN) du certificat associé à cet ordinateur.
    
- Sélectionnez l’une des options suivantes :
    
    **Utiliser toutes les adresses IP configurées**: sélectionnez cette option pour utiliser toutes les adresses IP configurées sur l’ordinateur.
    
    > [!IMPORTANT]
    > Si l’ordinateur est doté de plusieurs adresses IP, vous devez savoir que les services associés à cet ordinateur utiliseront toutes les adresses IP de tous les services. Si un serveur ou un service d’écoute attend la communication d’une adresse IP et d’un port spécifiques, le service n’est peut-être pas le meilleur choix de l’adresse IP à écouter. 
  
    **Limiter l’utilisation des services aux adresses IP sélectionnées**: sélectionnez cette option si vous souhaitez définir des adresses IP spécifiques pour l' **adresse IP principale** que cet ordinateur écoute pour la communication à partir d’autres ordinateurs et pools dans le déploiement. Définissez l' **adresse IP PSTN** pour l’adresse IP spécifique que l’ordinateur et le service écoutent pour les communications et qui envoient des communications à la passerelle PSTN ou au PBX IP défini.
    

