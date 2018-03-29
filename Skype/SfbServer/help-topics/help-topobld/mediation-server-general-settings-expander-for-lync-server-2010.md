---
title: Développement de paramètres général de serveur de médiation pour Lync Server 2010
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 'Vous modifiez les propriétés des serveurs de médiation dans cette boîte de dialogue. Sur le côté gauche est un ensemble de liens rapides pour vous faire passer les paramètres pour les paramètres généraux, les paramètres de saut suivant et les paramètres de la passerelle RTPC. Dans chaque section sont les suivants :'
ms.openlocfilehash: bc5016c9dbeb6b0693444f930c9883b1736258d2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a>Développement de paramètres général de serveur de médiation pour Lync Server 2010
 
Vous modifiez les propriétés des serveurs de médiation dans cette boîte de dialogue. Sur le côté gauche est un ensemble de liens rapides pour vous faire passer les paramètres pour les paramètres généraux, les paramètres de saut suivant et les paramètres de la passerelle RTPC. Dans chaque section sont les suivants :
  
 **Général**:
  
- **Nom de domaine complet**: vous modifiez le nom de domaine pleinement qualifié du serveur de médiation
    
- **Associations**: cochez la case **pool d’associer le bord (pour les composants de support)** , sélectionnez un serveur de transport Edge ou à un pool de bord pour le serveur de médiation à utiliser comme le chemin d’accès au support pour l’accès externe.
    
 **Tronçon suivant**:
  
- **Sélection de saut suivante**: sélectionner dans une liste le pool Front-End ou de serveur frontal à utiliser en tant que le chemin d’accès pour le serveur de médiation à utiliser pour communiquer avec votre déploiement.
    
 **Passerelle PSTN**:
  
 **Passerelle PSTN de serveur de médiation**:
  
- **Ports d’écoute**: définir les ports qui écoute sur le serveur de médiation. Vous pouvez définir un port pour la sécurité de la couche transport ou **TLS** ou **TCP**, ou le protocole de contrôle de transport. Pour l’entrée de port pour TCP soit disponible, vous devez sélectionner la case à cocher pour **Activer le TCP port**. 
    
    > [!IMPORTANT]
    > Reportez-vous à la documentation et configuration pour votre passerelle de réseau téléphonique public commuté pour déterminer si vous devez activer et définir les valeurs de port TLS, TCP ou les deux. TLS est un protocole plus sécurisé, l’utilisation de certificats pour crypter le trafic entre le serveur de médiation et la passerelle RTC. Les passerelles RTPC pas tous en charge TLS. 
  
- Une liste des puits SIP et les passerelles qui sont définis et configurés pour votre déploiement est répertoriée. Si aucune entrée n’est présente, il n’y aucun SIP troncs ou des passerelles RTPC configurés pour votre déploiement. Vous définissez et configurez les trunks et passerelles sous **Composants partagés** dans le Générateur de topologie.
    
## <a name="see-also"></a>Voir aussi

#### 

[Vue d’ensemble des SIP Trunking](http://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)
  
[Options de déploiement de passerelle RTPC](http://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)

