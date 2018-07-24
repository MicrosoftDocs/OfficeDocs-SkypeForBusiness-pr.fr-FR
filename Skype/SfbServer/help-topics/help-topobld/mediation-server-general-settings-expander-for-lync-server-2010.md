---
title: Expanseur des paramètres de général du serveur de médiation pour Lync Server 2010
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 'Vous modifiez les propriétés des serveurs de médiation dans cette boîte de dialogue. Sur le côté gauche est un ensemble de liens rapides pour les paramètres pour les paramètres généraux, paramètres du tronçon suivant et les paramètres de la passerelle PSTN. Dans chaque section sont les paramètres suivants :'
ms.openlocfilehash: 0d3601731473b3d48b8199ee69f1e3ed18e806b9
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20967795"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a>Expanseur des paramètres de général du serveur de médiation pour Lync Server 2010
 
Vous modifiez les propriétés des serveurs de médiation dans cette boîte de dialogue. Sur le côté gauche est un ensemble de liens rapides pour les paramètres pour les paramètres généraux, paramètres du tronçon suivant et les paramètres de la passerelle PSTN. Dans chaque section sont les paramètres suivants :
  
 **Général**:
  
- **Nom de domaine complet**: vous modifiez le nom de domaine complet du serveur de médiation
    
- **Associations**: activez la case à cocher **pool Edge associé (pour les composants médias)** et sélectionnez un serveur Edge ou pool de serveurs Edge pour le serveur de médiation à utiliser en tant que le chemin d’accès des médias pour l’accès externe.
    
 **Tronçon suivant**:
  
- **Sélection du tronçon suivant**: sélectionnez dans la liste le pool frontal ou serveur frontal à utiliser en tant que le chemin d’accès du serveur de médiation à utiliser pour communiquer avec votre déploiement.
    
 **Passerelle PSTN**:
  
 **Passerelle PSTN de serveur de médiation**:
  
- **Ports d’écoute**: définir les ports d’écoute sur le serveur de médiation. Vous pouvez définir un port pour **TLS** ou transport layer security, ou **TCP**, ou le protocole de transport. Pour l’entrée de port TCP soit disponible, vous devez sélectionner la case à cocher pour **le port TCP activer**. 
    
    > [!IMPORTANT]
    > Consultez les paramètres de configuration et de la documentation de votre passerelle de réseau téléphonique commuté pour déterminer si vous souhaitez activer et définir les valeurs de ports TLS, TCP ou les deux. TLS est un protocole plus sécurisé, l’utilisation de certificats pour chiffrer le trafic entre le serveur de médiation et la passerelle PSTN. Pas toutes les passerelles PSTN prend en charge TLS. 
  
- Une liste de jonctions SIP et les passerelles qui sont définis et configurés pour votre déploiement est répertoriée. Si aucune entrée n’est présent, il n’existe aucune jonctions SIP ou des passerelles PSTN configurés pour votre déploiement. Vous définissez et configurez des jonctions et des passerelles sous **Composants partagés** dans le Générateur de topologie.
    
## <a name="see-also"></a>Voir aussi

[Vue d’ensemble d’une jonction SIP](http://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)
  
[Options de déploiement de passerelle PSTN](http://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)