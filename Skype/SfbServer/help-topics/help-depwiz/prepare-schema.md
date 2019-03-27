---
title: Préparer un schéma
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
description: Pour préparer le schéma pour les Services de domaine Active Directory, vous exécutez l’étape de préparation du schéma dans le Skype pour l’Assistant Déploiement Business Server. Cliquez sur Exécuter pour commencer la préparation du schéma. L’étape de préparation du schéma lit les fichiers de définition de schéma fourni dans le répertoire de fonctionnalité/Microsoft Lync Server 2013/déploiement/configuration des fichiers sur le système de l’Assistant déploiement est en cours d’exécution. Ces fichiers sont également disponibles sur le support d’installation dans le répertoire/schéma prise en charge. L’étape Préparer un schéma développera le schéma et rapportera le statut du processus. Elle vous notifiera également l’achèvement du processus. L’écran de résumé vous permettra d’afficher les journaux du processus. Passez en revue les journaux pour vous assurer que la préparation est terminée et qu’elle a abouti.
ms.openlocfilehash: 8565a3474b309820714949b5aa6f4544c72a23bd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891007"
---
# <a name="prepare-schema"></a>Préparer un schéma
 
Pour préparer le schéma pour les Services de domaine Active Directory, vous exécutez l’étape de préparation du schéma dans le Skype pour l’Assistant Déploiement Business Server. Cliquez sur **Exécuter** pour commencer la préparation du schéma. L’étape Préparer un schéma lit les fichiers de définition de schéma fournis dans le répertoire \Program Files\Microsoft Lync Server 2013\Deployment\Setup sur le système sur lequel l’Assistant Déploiement s’exécute. Ces fichiers sont également disponibles sur le support d’installation, dans le répertoire \Support\Schema. L’étape Préparer un schéma développera le schéma et rapportera le statut du processus. Elle vous notifiera également l’achèvement du processus. L’écran de résumé vous permettra d’afficher les journaux du processus. Passez en revue les journaux pour vous assurer que la préparation est terminée et qu’elle a abouti.
  
> [!IMPORTANT]
> Pour étendre le schéma, vous devez être connecté au domaine en tant que membre du groupe Administrateurs du schéma et du groupe Administrateurs d’entreprise. 
  
Classes et attributs sont ajoutés pour étendre le schéma Active Directory Domain Services pour prendre en charge Skype pour serveur Business Server 2015, service et les objets utilisateur. Avant d’étendre le schéma, effectuez une sauvegarde de l’état du système du contrôleur de domaine qui contient le rôle de contrôleur de schéma. Pour plus d’informations sur le processus de sauvegarde de Windows Server 2008 R2 avec SP1, voir [https://go.microsoft.com/fwlink/p/?linkId=207198](https://go.microsoft.com/fwlink/p/?linkId=207198). Pour Windows Server 2003 et Windows Server 2003 R2, voir [https://go.microsoft.com/fwlink/p/?linkId=207199](https://go.microsoft.com/fwlink/p/?linkId=207199).
  
> [!CAUTION]
> Cette opération est irréversible. Vous devez faire tout votre possible pour limiter l’impact potentiel d’un échec de l’extension du schéma et pour garantir la réussite de l’extension du schéma. Ceci est particulièrement important en cas de perte de communication ou de toute autre défaillance côté serveur. Vous devez effectuer une sauvegarde du contrôleur de domaine maître de schéma et une sauvegarde complète d’Active Directory. 
  
Pour effectuer une sauvegarde du contrôleur de domaine maître de schéma et une sauvegarde complète d’Active Directory :
  
1. Déconnectez du réseau le contrôleur de domaine qui contient le rôle de contrôleur de schéma.
    
2. Effectuez une sauvegarde de l’état du système du contrôleur de domaine qui contient le contrôleur de schéma.
    
3. Étendez le schéma.
    
4. Lorsque l’extension aboutit, reconnectez le contrôleur de domaine au réseau et assurez-vous que la réplication est active et qu’elle fonctionne.
    
5. Dans le cas improbable d’un échec, restaurez l’état système du contrôleur de domaine et Active Directory à l’aide de la sauvegarde de l’état du système que vous avez effectuée précédemment.
    
> [!NOTE]
> Si vous avez besoin passer en revue les fichiers journaux qui sont créés par le Skype pour l’Assistant de déploiement Business Server, vous trouverez les fichiers sur l’ordinateur où a été exécuté l’Assistant déploiement, dans le répertoire des utilisateurs de l’utilisateur Active Directory qui a exécuté l’étape. Par exemple, si l’utilisateur est connecté en tant qu’administrateur de domaine dans le domaine Contoso.net, les fichiers journaux se trouvent dans : C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

