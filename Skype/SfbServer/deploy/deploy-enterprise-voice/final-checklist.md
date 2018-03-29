---
title: Appeler admission contrôle final du pré-déploiement pour Skype Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: Liste de vérification finale pour le déploiement d’appeler contrôle d’Admission (CAC) dans Skype pour Business Server Voix Entreprise.
ms.openlocfilehash: 9971d59f0b9c3c2c1f9bfd5e8176122715b19d20
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server-2015"></a>Déploiement du contrôle d’admission des appels : liste de vérification finale pour Skype Entreprise Server 2015
 
Liste de vérification finale pour le déploiement d’appeler contrôle d’Admission (CAC) dans Skype pour Business Server Voix Entreprise. 
  
Servez-vous de la liste de contrôle suivante pour vérifier que vous avez exécuté toutes les tâches de configuration nécessaires au déploiement du contrôle d’admission des appels (CAC).
  
- Si un ou plusieurs serveurs Edge sont déployés, chaque adresse de l’interface externe doit être ajouté à la liste des sous-réseaux dans les paramètres de configuration réseau, avec un masque de 32 bits. Vous devez également associer ce sous-réseau (adresse IP) à l’ID de site réseau pour l’emplacement géographique auquel le service Edge A/V est déployé.
    
    > [!NOTE]
    > Les serveurs Edge n’êtes pas obligés de mettre en œuvre la CAC. 
  
- Assurez-vous que le CAC est activé, comme spécifié dans [le contrôle d’admission appel activer dans Skype pour Business Server 2015](enable-call-admission-control.md).
    
- Vérifiez que le contrôle d’admission des appels est activé sur tous les sites centraux. Pour ce faire par le biais du Générateur de topologie. Si un avertissement est généré lors de la publication, *ne le faites pas* l’ignorer.
    
- Vérifiez que tous les sous-réseaux gérés dans le réseau d’entreprise sont configurés dans les paramètres de configuration réseau. Il est également essentiel que chaque sous-réseau est associé à un site de réseau, comme expliqué dans les [régions de réseau, des sites et des sous-réseaux dans Skype pour entreprise 2015 déployer](deploy-network.md).
    
- Vérifiez que les adresses IP ou de sous-réseau de tous les serveurs frontaux, SBA (Survivable Branch Appliances), serveurs de conférence audio/vidéo (s’ils figurent dans un pool distinct) et serveurs de médiation sont configurées dans les paramètres de configuration réseau.
    

