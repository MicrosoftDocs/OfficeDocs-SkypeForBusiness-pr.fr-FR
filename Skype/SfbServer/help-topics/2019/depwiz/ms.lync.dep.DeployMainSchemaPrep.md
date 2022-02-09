---
title: Préparer un schéma
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
ROBOTS: NOINDEX, NOFOLLOW
description: Pour préparer le schéma pour les services de domaine Active Directory, exécutez l’étape Préparer le schéma dans l’Skype Entreprise Server Déploiement. Cliquez sur Exécuter pour commencer la préparation du schéma.
ms.openlocfilehash: 43496aa2b9d3ec40f4c79aed0e20824ee7ef1494
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62404326"
---
# <a name="prepare-schema"></a>Préparer un schéma
 
Pour préparer le schéma pour les services de domaine Active Directory, exécutez l’étape Préparer le schéma dans l’Skype Entreprise Server Déploiement. Cliquez sur **Exécuter** pour commencer la préparation du schéma. L’étape Préparer le schéma lit les fichiers de définition de schéma fournis dans le répertoire \Program Files\Skype Entreprise Server 2019\Deployment\Setup sur le système sur qui l’Assistant Déploiement est en cours d’exécution. Ces fichiers sont également disponibles sur le support d’installation, dans le répertoire \Support\Schema. L’étape Préparer un schéma développera le schéma et rapportera le statut du processus. Elle vous notifiera également l’achèvement du processus. L’écran de résumé vous permettra d’afficher les journaux du processus. Passez en revue les journaux pour vous assurer que la préparation était complète et qu’elle a abouti.
  
> [!IMPORTANT]
> Pour étendre le schéma, vous devez être connecté au domaine en tant que membre du groupe Administrateurs du schéma et du groupe Administrateurs d’entreprise. 
  
Des classes et des attributs sont ajoutés pour étendre le schéma des services de domaine Active Directory pour prendre en charge Skype Entreprise Server serveur, service et objets utilisateur. Avant d’étendre le schéma, effectuez une sauvegarde de l’état du système du contrôleur de domaine qui contient le rôle de contrôleur de schéma. 
  
> [!CAUTION]
> Cette opération est irréversible. Vous devez faire tout votre possible pour limiter l’impact potentiel d’un échec de l’extension du schéma et pour garantir la réussite de l’extension du schéma. Ceci est particulièrement important en cas de perte de communication ou de toute autre défaillance côté serveur. Vous devez effectuer une sauvegarde du contrôleur de domaine contrôleur de schéma et une sauvegarde complète d’Active Directory. 
  
Pour effectuer une sauvegarde du contrôleur de domaine contrôleur de schéma et une sauvegarde complète d’Active Directory :
  
1. Déconnectez du réseau le contrôleur de domaine qui contient le rôle de contrôleur de schéma.
    
2. Effectuez une sauvegarde de l’état du système du contrôleur de domaine qui contient le contrôleur de schéma.
    
3. Étendez le schéma.
    
4. Lorsque l’extension aboutit, reconnectez le contrôleur de domaine au réseau et assurez-vous que la réplication est active et qu’elle fonctionne.
    
5. Dans le cas peu probable d’une défaillance d’extension de schéma, restituer l’état du système du contrôleur de domaine et d’Active Directory à l’aide de la sauvegarde de l’état du système que vous avez précédemment fait.
    
> [!NOTE]
> Si vous devez passer en revue les fichiers journaux créés par l’Assistant Déploiement de Skype Entreprise Server, vous pouvez trouver les fichiers sur l’ordinateur sur lequel l’Assistant Déploiement a été exécuté, dans le répertoire Utilisateurs de l’utilisateur Active Directory qui a exécuté l’étape. Par exemple, si l’utilisateur s’est connecté en tant qu’administrateur de domaine dans le Contoso.net de domaine, les fichiers journaux se trouvent dans : C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

