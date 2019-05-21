---
title: Liste de vérification de déploiement des contrôles d’admission des appels pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: Liste de vérification finale pour le déploiement du contrôle d’admission des appels (CAC) dans Skype entreprise Server Voice.
ms.openlocfilehash: fab6472d931d0475a3e3b0a0f413fce7775d7a15
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34281590"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a>Déploiement du contrôle d’admission des appels: liste de vérification finale pour Skype entreprise Server
 
Liste de vérification finale pour le déploiement du contrôle d’admission des appels (CAC) dans Skype entreprise Server Voice. 
  
Servez-vous de la liste de contrôle suivante pour vérifier que vous avez exécuté toutes les tâches de configuration nécessaires au déploiement du contrôle d’admission des appels (CAC).
  
- Si au moins un serveur Edge est déployé, chaque adresse IP de l’interface externe doit être ajoutée à la liste des sous-réseaux dans les paramètres de configuration du réseau, avec un masque de bits de 32. Vous devez également associer ce sous-réseau (adresse IP) à l’ID de site réseau pour l’emplacement géographique auquel le service Edge A/V est déployé.
    
    > [!NOTE]
    > Il n’est pas nécessaire de mettre en place des serveurs de périphérie pour le CAC. 
  
- Assurez-vous que le contrôle CAC est activé, tel qu’il est spécifié dans [activer le contrôle d’admission des appels dans Skype entreprise Server](enable-call-admission-control.md).
    
- Vérifiez que le contrôle d’admission des appels est activé sur tous les sites centraux. Cette opération peut être réalisée par le biais du générateur de topologie. Si un message d’avertissement est généré lors de la publication, ne l’ignorez *pas* .
    
- Vérifiez que tous les sous-réseaux gérés dans le réseau d’entreprise sont configurés dans les paramètres de configuration réseau. Il est également essentiel que chaque sous-réseau soit associé à un site réseau, comme décrit dans la rubrique [déploiement de régions réseau, de sites et de sous-réseaux dans Skype entreprise](deploy-network.md).
    
- Vérifiez que les adresses IP ou de sous-réseau de tous les serveurs frontaux, SBA (Survivable Branch Appliances), serveurs de conférence audio/vidéo (s’ils figurent dans un pool distinct) et serveurs de médiation sont configurées dans les paramètres de configuration réseau.
    

