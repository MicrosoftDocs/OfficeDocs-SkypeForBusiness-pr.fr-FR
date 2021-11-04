---
title: Ajouter un magasin fichiers de conversation permanente
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatFileStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e1068706-ff61-4a98-8e51-4202111d936a
description: Vous devez indiquer un partage de fichiers à utiliser comme magasin de fichiers pour le serveur Standard Edition ou le pool frontal Enterprise Edition. Vous pouvez utiliser un partage de fichiers existant pour le magasin de fichiers ou spécifier un nouveau partage de fichiers en spécifiant le nom de domaine complet (FQDN) du serveur de fichiers sur lequel situer le partage de fichiers et un nom de dossier pour le nouveau partage de fichiers.
ms.openlocfilehash: d061ff6e3bd084fef4ebf80c84c5e14a127afa91
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60747830"
---
# <a name="add-persistent-chat-file-store"></a>Ajouter un magasin fichiers de conversation permanente
 
Vous devez indiquer un partage de fichiers à utiliser comme magasin de fichiers pour le serveur Standard Edition ou le pool frontal Enterprise Edition. Vous pouvez utiliser un partage de fichiers existant pour le magasin de fichiers ou spécifier un nouveau partage de fichiers en spécifiant le nom de domaine complet (FQDN) du serveur de fichiers sur lequel situer le partage de fichiers et un nom de dossier pour le nouveau partage de fichiers.
  
> [!IMPORTANT]
> Le partage de fichiers pour Skype Entreprise Server ne peut pas se trouver sur Êdition Entreprise serveur frontal, mais peut se trouver sur un Édition Standard serveur. 
  
> [!IMPORTANT]
> Avant de créer le partage de fichiers, vous pouvez le définir dans le Générateur de topologie, mais vous devez créer le partage de fichiers à l’emplacement que vous définissez avant de publier la topologie. 
  
> [!IMPORTANT]
> Lorsque vous ajoutez un serveur de conversation permanente ou un pool de serveurs de conversation permanente à votre topologie, le Générateur de topologie doit pouvoir configurer le magasin de fichiers et configurer des listes de contrôle d’accès discrétionnaire (DAC) sur le partage de fichiers à utiliser pour le magasin de fichiers. Pour cela, lorsque vous exécutez le Générateur de topologie pour publier la nouvelle topologie, vous devez être connecté avec un compte qui dispose des autorisations de contrôle complètes (lecture/écriture/modification) pour le partage de fichiers. 
  
## <a name="see-also"></a>Voir aussi

[Planifier le serveur de conversation permanente dans Skype Entreprise Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Ajouter un serveur de conversation permanente à votre topologie Skype Entreprise Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Configuration matérielle et logicielle requise pour le serveur de conversation permanente Skype Entreprise Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Server requirements for Skype Entreprise Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Informations de base sur la topologie Skype Entreprise Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md)
