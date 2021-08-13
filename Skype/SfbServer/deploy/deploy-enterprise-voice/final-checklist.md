---
title: Liste de vérification finale du déploiement du contrôle d’admission des appels Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: Liste de vérification finale pour le déploiement du contrôle d’admission des appels dans Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: 89893e846d37a2a10cbf33de53b8426a0b9d3d642846455e1415991903b0f3e3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54338732"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a>Déploiement du contrôle d’admission des appels : liste de contrôle finale pour Skype Entreprise Server
 
Liste de vérification finale pour le déploiement du contrôle d’admission des appels dans Skype Entreprise Server Voix Entreprise. 
  
Utilisez la liste de vérification suivante pour vérifier que vous avez effectué toutes les tâches de configuration nécessaires au déploiement du contrôle d’admission des appels (CAC).
  
- Si un ou plusieurs serveurs Edge sont déployés, chaque adresse IP de l’interface externe doit être ajoutée à la liste de sous-réseaux dans les paramètres de configuration réseau, avec un masque de 32 bits. Vous devez également associer ce sous-réseau (adresse IP) à l’ID de site réseau pour l’emplacement géographique où est déployé le service Edge A/V.
    
    > [!NOTE]
    > Les serveurs Edge ne sont pas requis pour implémenter le service Cac. 
  
- Assurez-vous que le contrôle d’admission des appels est activé, comme indiqué dans Activer le contrôle d’admission des [appels dans Skype Entreprise Server](enable-call-admission-control.md).
    
- Vérifiez que le contrôle d’admission des appels est activé sur tous les sites centraux. Pour ce faire, vous pouvez utiliser le Générateur de topologies. Si un avertissement est généré lors de la publication,  *ne l’ignorez*  pas.
    
- Vérifiez que tous les sous-réseaux qui sont gérés dans le réseau d’entreprise sont configurés dans les paramètres de configuration réseau. Il est également essentiel que chaque sous-réseau soit associé à un site réseau, comme expliqué dans Déployer des régions [réseau, des sites](deploy-network.md)et des sous-réseaux dans Skype Entreprise .
    
- Vérifiez que les adresses IP ou de sous-réseau de tous les serveurs frontaux, SBA (Survivable Branch Appliances), serveurs de conférence Audio/Vidéo (s’ils figurent dans un pool distinct) et serveurs de médiation sont configurées dans les paramètres de configuration réseau.
    

