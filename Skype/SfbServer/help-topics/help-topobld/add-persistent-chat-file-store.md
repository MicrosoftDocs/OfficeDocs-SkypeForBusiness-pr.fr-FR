---
title: Ajouter un magasin de fichiers de conversation permanente
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1068706-ff61-4a98-8e51-4202111d936a
description: Vous devez indiquer un partage de fichiers à utiliser comme magasin de fichiers pour le serveur Standard Edition ou le pool frontal Enterprise Edition. Vous pouvez utiliser un partage de fichiers existant pour le magasin de fichiers ou spécifier un nouveau partage de fichiers en spécifiant le nom de domaine complet (FQDN) du serveur de fichiers sur lequel le partage de fichiers doit se trouver et un nom de dossier pour le nouveau partage de fichiers.
ms.openlocfilehash: 6463cb2c572be5d367e8788fc121ed0981bcb8a9
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/19/2018
ms.locfileid: "19503822"
---
# <a name="add-persistent-chat-file-store"></a>Ajouter un magasin de fichiers de conversation permanente
 
Vous devez indiquer un partage de fichiers à utiliser comme magasin de fichiers pour le serveur Standard Edition ou le pool frontal Enterprise Edition. Vous pouvez utiliser un partage de fichiers existant pour le magasin de fichiers ou spécifier un nouveau partage de fichiers en spécifiant le nom de domaine complet (FQDN) du serveur de fichiers sur lequel le partage de fichiers doit se trouver et un nom de dossier pour le nouveau partage de fichiers.
  
> [!IMPORTANT]
> Le partage de fichiers pour Skype pour Business Server ne peut pas se trouver sur le serveur Enterprise Edition avant, mais il peut se trouver sur un serveur Standard Edition server. 
  
> [!IMPORTANT]
> Avant de créer le partage de fichiers, vous pouvez le définir dans le générateur de topologie, mais vous devez créer le partage de fichiers à l’emplacement défini avant la publication de la topologie. 
  
> [!IMPORTANT]
> Lorsque vous ajoutez un serveur de conversation permanente ou Persistent Chat Server pool à votre topologie, le Générateur de topologie doit être en mesure de configurer le fichier, stocker et configurer le contrôle d’accès discrétionnaire listes (DACL) sur le partage de fichiers à utiliser pour le magasin de fichiers. À cet effet, lorsque vous exécutez le générateur de topologie pour publier la nouvelle topologie, vous devez être connecté avec un compte disposant d’autorisations de contrôle intégrales (lecture/écriture/modification) pour le partage de fichiers. 
  
## <a name="see-also"></a>Voir aussi

[Planifier un serveur de conversation permanente dans Skype Entreprise Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Ajouter des serveurs de conversation permanente à votre Skype pour Business Server 2015 topologie](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Configuration logicielle et matérielle requise pour le serveur de conversation permanente dans Skype Entreprise Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Configuration serveur requise pour Skype Entreprise Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Notions de base de la topologie pour Skype Entreprise Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md)