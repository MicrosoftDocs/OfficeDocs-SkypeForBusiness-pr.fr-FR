---
title: Préparer un schéma
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
description: Pour préparer le schéma pour les services de domaine Active Directory (AD FS), exécutez l’étape préparer le schéma dans l’Assistant Déploiement de Skype entreprise Server. Cliquez sur Exécuter pour commencer la préparation du schéma. L’étape préparer le schéma lit les fichiers de définition de schéma fournis dans le dossier/Program Files/Microsoft Lync Server 2013/déploiement/installation sur le système sur lequel l’Assistant déploiement s’exécute. Ces fichiers sont également disponibles sur le média d’installation dans le répertoire support/schéma. L’étape Préparer un schéma développera le schéma et rapportera le statut du processus. Elle vous notifiera également l’achèvement du processus. L’écran de résumé vous permettra d’afficher les journaux du processus. Passez en revue les journaux pour vous assurer que la préparation est terminée et qu’elle a abouti.
ms.openlocfilehash: fd1e79411c9820013954be0add7b68c326188e9e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41700819"
---
# <a name="prepare-schema"></a>Préparer un schéma
 
Pour préparer le schéma pour les services de domaine Active Directory (AD FS), exécutez l’étape préparer le schéma dans l’Assistant Déploiement de Skype entreprise Server. Cliquez sur **Exécuter** pour commencer la préparation du schéma. L’étape Préparer un schéma lit les fichiers de définition de schéma fournis dans le répertoire \Program Files\Microsoft Lync Server 2013\Deployment\Setup sur le système sur lequel l’Assistant Déploiement s’exécute. Ces fichiers sont également disponibles sur le support d’installation, dans le répertoire \Support\Schema. L’étape Préparer un schéma développera le schéma et rapportera le statut du processus. Elle vous notifiera également l’achèvement du processus. L’écran de résumé vous permettra d’afficher les journaux du processus. Passez en revue les journaux pour vous assurer que la préparation est terminée et qu’elle a abouti.
  
> [!IMPORTANT]
> Pour étendre le schéma, vous devez être connecté au domaine en tant que membre du groupe Administrateurs du schéma et du groupe Administrateurs d’entreprise. 
  
Les classes et attributs sont ajoutés pour étendre le schéma des services de domaine Active Directory pour prendre en charge les objets serveur, service et utilisateur de Skype entreprise Server 2015. Avant d’étendre le schéma, effectuez une sauvegarde de l’état du système du contrôleur de domaine qui contient le rôle de contrôleur de schéma. Pour plus d’informations sur le processus de sauvegarde de Windows Server 2008 R2 avec [https://go.microsoft.com/fwlink/p/?linkId=207198](https://go.microsoft.com/fwlink/p/?linkId=207198)SP1, voir. Pour Windows Server 2003 et Windows Server 2003 R2, voir [https://go.microsoft.com/fwlink/p/?linkId=207199](https://go.microsoft.com/fwlink/p/?linkId=207199).
  
> [!CAUTION]
> Cette opération est irréversible. Vous devez faire tout votre possible pour limiter l’impact potentiel d’un échec de l’extension du schéma et pour garantir la réussite de l’extension du schéma. Ceci est particulièrement important en cas de perte de communication ou de toute autre défaillance côté serveur. Vous devez effectuer une sauvegarde du contrôleur de domaine du maître de schéma et une sauvegarde complète d’Active Directory. 
  
Pour effectuer une sauvegarde du contrôleur de domaine du maître de schéma et d’une sauvegarde complète d’Active Directory :
  
1. Déconnectez du réseau le contrôleur de domaine qui contient le rôle de contrôleur de schéma.
    
2. Effectuez une sauvegarde de l’état du système du contrôleur de domaine qui contient le contrôleur de schéma.
    
3. Étendez le schéma.
    
4. Lorsque l’extension aboutit, reconnectez le contrôleur de domaine au réseau et assurez-vous que la réplication est active et qu’elle fonctionne.
    
5. Dans l’éventualité improbable d’un échec de l’extension du schéma, restaurez l’état du système du contrôleur de domaine et d’Active Directory à l’aide de la sauvegarde de l’état du système que vous avez effectuée auparavant.
    
> [!NOTE]
> Si vous avez besoin de passer en revue les fichiers journaux créés par l’Assistant Déploiement de Skype entreprise Server, vous pouvez rechercher les fichiers sur l’ordinateur sur lequel l’Assistant déploiement a été exécuté, dans l’annuaire utilisateurs de l’utilisateur Active Directory qui a exécuté l’étape. Par exemple, si l’utilisateur connecté en tant qu’administrateur de domaine dans le domaine Contoso.net, les fichiers journaux se trouvent dans : C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

