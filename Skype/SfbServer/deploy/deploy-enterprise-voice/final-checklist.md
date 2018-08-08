---
title: Appeler liste finale du déploiement de contrôle d’admission des appels de Skype pour Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: Liste de vérification finale pour le déploiement d’admission des appels contrôle appels (CAC) dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: e5791aa6f3b32e423f36021314bec930fa7f74e5
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21025673"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a>Déploiement du contrôle d’admission des appels : liste de vérification finale pour Skype pour Business Server
 
Liste de vérification finale pour le déploiement d’admission des appels contrôle appels (CAC) dans Skype pour Business Server Enterprise Voice. 
  
Servez-vous de la liste de contrôle suivante pour vérifier que vous avez exécuté toutes les tâches de configuration nécessaires au déploiement du contrôle d’admission des appels (CAC).
  
- Si un ou plusieurs serveurs Edge sont déployés, chaque adresse de l’interface externe doit être ajouté à la liste de sous-réseau dans les paramètres de configuration réseau, avec un masque de 32 bits. Vous devez également associer ce sous-réseau (adresse IP) à l’ID de site réseau pour l’emplacement géographique auquel le service Edge A/V est déployé.
    
    > [!NOTE]
    > Serveurs de périphérie ne sont pas tenus d’implémenter CAC. 
  
- Assurez-vous que CAC est activé, comme spécifié dans [le contrôle d’admission des appels d’appel activer dans Skype pour Business Server](enable-call-admission-control.md).
    
- Vérifiez que le contrôle d’admission des appels est activé sur tous les sites centraux. Pour ce faire par le biais du Générateur de topologies. Si un avertissement est généré lorsque vous publiez, *ne mais pas* l’ignorer.
    
- Vérifiez que tous les sous-réseaux gérés dans le réseau d’entreprise sont configurés dans les paramètres de configuration réseau. Il est également indispensable que tous les sous-réseaux associés à un site réseau, comme expliqué dans les [régions de réseau de déploiement, des sites et sous-réseaux de Skype pour les entreprises](deploy-network.md).
    
- Vérifiez que les adresses IP ou de sous-réseau de tous les serveurs frontaux, SBA (Survivable Branch Appliances), serveurs de conférence audio/vidéo (s’ils figurent dans un pool distinct) et serveurs de médiation sont configurées dans les paramètres de configuration réseau.
    

