---
title: Déployer le rôle serveur VIS dans Skype Entreprise Server
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
ms.collection: IT_Skype16
ms.assetid: b6401e67-59fe-4419-a0ab-ffac88e67632
description: 'Résumé : Déployez le rôle vis (Video Interop Server) dans Skype Entreprise Server.'
ms.openlocfilehash: 773e2ddf790aa1b6c36ff6926d8bc4d16ea613f5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801964"
---
# <a name="deploy-the-vis-server-role-in-skype-for-business-server"></a>Déployer le rôle serveur VIS dans Skype Entreprise Server
 
**Résumé :** Déployez le rôle VIS (Video Interop Server) dans Skype Entreprise Server.
  
Pour configurer le service VIS sur le serveur qui vient d’être créé dans le Générateur de topologie, démarrez l’Assistant Déploiement de Skype Entreprise Server, appuyez sur Installer ou mettre à jour le système Skype Entreprise **Server** et suivez les étapes suivantes dans l’Assistant :
  
1.  Sélectionnez **Installer le magasin de configurations local.**
    
2. Sélectionnez **Le programme d’installation ou supprimez les composants Skype Entreprise Server.**
    
3. Select **Request, Install or Assign Certificates**.
    
4. Sélectionnez **Démarrer les services.**
    
Le logiciel de ce service est maintenant installé et en cours d’exécution. Vous pouvez ouvrir l’outil MMC Services pour voir si le service **Skype Entreprise Server Video Interop Server** est en cours d’exécution avec d’autres services Skype Entreprise Server. Ensuite, vous devez configurer le serveur VIS ou le pool.
## <a name="see-also"></a>Voir aussi

[Configurer le serveur d’opation vidéo dans Skype Entreprise Server](configure-the-vis.md)
