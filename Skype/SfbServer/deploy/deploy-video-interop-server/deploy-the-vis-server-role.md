---
title: Déployer le rôle de serveur VIS Skype pour Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6401e67-59fe-4419-a0ab-ffac88e67632
description: 'Résumé : Déployez le rôle de serveur d’interopérabilité vidéo (VIS) dans Skype pour Business Server.'
ms.openlocfilehash: b52980a727ad0ce13e45e2c833c971598afafa1e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20993442"
---
# <a name="deploy-the-vis-server-role-in-skype-for-business-server"></a>Déployer le rôle de serveur VIS Skype pour Business Server
 
**Résumé :** Déployer le rôle de serveur d’interopérabilité vidéo (VIS) dans Skype pour Business Server.
  
Pour configurer le service de rapport sur le serveur créé dans le Générateur de topologie, démarrer le Skype pour l’Assistant de déploiement de serveur d’entreprise, appuyez sur **installer ou mise à jour Skype pour Business Server System** et suivez ces étapes dans l’Assistant :
  
1.  Sélectionnez **Installer le magasin de configurations local**.
    
2. Sélectionnez **installer ou supprimer des Skype pour les composants de serveur d’entreprise**.
    
3. Sélectionnez **Demander, installer ou assigner les certificats**.
    
4. Sélectionnez **Démarrer les services**.
    
Le logiciel de ce service est maintenant installé et opérationnel. Vous pouvez ouvrir l’outil de mmc Services pour voir si le service **Skype pour Business interopérabilité vidéo Server** est en cours d’exécution ainsi que d’autres Skype pour les services Business Server. Vous devez ensuite configurer le serveur ou le pool VIS.
## <a name="see-also"></a>Voir aussi

[Configurer le serveur d’interopérabilité vidéo dans Skype pour Business Server](configure-the-vis.md)