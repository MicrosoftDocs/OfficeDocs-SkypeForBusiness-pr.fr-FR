---
title: Migrer des groupes de réponses
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Une fois que vos utilisateurs sont déplacés vers Skype pour les pools d’entreprise Server 2019, vous pouvez migrer vos groupes Response Group. Migration de Response Group groupes comprend la copie des groupes d’agents, les files d’attente, les flux de travail, les fichiers audio et déplacer les objets de contact de Response Group à partir du déploiement hérité vers le Skype pour Business Server 2019 pool. Après avoir fait migrer vos groupes Response Group hérités, les appels vers les groupes Response Group sont gérés par l’application Response Group dans le Skype pour Business Server 2019 pool. Les appels vers les groupes Response Group sont ne sont plus gérés par le pool hérité.
ms.openlocfilehash: 89149210e8041fbc84834cec83e1c1fe13d0765c
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372936"
---
# <a name="migrate-response-groups"></a>Migrer des groupes de réponses

Une fois que vos utilisateurs sont déplacés vers Skype pour les pools d’entreprise Server 2019, vous pouvez migrer vos groupes Response Group. Migration de Response Group groupes comprend la copie des groupes d’agents, les files d’attente, les flux de travail, les fichiers audio et déplacer les objets de contact de Response Group à partir du déploiement hérité vers le Skype pour Business Server 2019 pool. Après avoir fait migrer vos groupes Response Group hérités, les appels vers les groupes Response Group sont gérés par l’application Response Group dans le Skype pour Business Server 2019 pool. Les appels vers les groupes Response Group sont ne sont plus gérés par le pool hérité.
  
> [!NOTE]
> Bien que vous pouvez migrer des groupes de réponses avant de déplacer tous les utilisateurs vers le Skype pour le pool d’entreprise Server 2019, nous vous recommandons de déplacer tout d’abord tous les utilisateurs. En particulier, les utilisateurs qui sont des agents response group n’auront pas toutes les fonctionnalités des nouvelles fonctionnalités jusqu'à ce qu’ils sont déplacés vers le Skype pour Business Server 2019 pool. 
  
Avant de migrer les groupes Response Group, vous devez avoir déployé un Skype pour le pool d’entreprise Server 2019 qui inclut l’application Response Group. L’application Response Group est installée et activée par défaut lors du déploiement d’Enterprise Voice. Vous pouvez vous assurer que l’application Response Group est installée en exécutant l’applet de commande **Get-CsService-ApplicationServer** . 
  
> [!NOTE]
> Vous pouvez créer nouveau Skype pour les groupes de réponse Business Server 2019 dans le Skype pour Business Server 2019 pool avant de migrer vos groupes Response Group hérités. 
  
Pour migrer des groupes de réponses à partir d’un pool hérité vers le Skype pour Business Server 2019, vous exécutez l’applet de commande **Move-CsRgsConfiguration** . 
  
> [!IMPORTANT]
> L’applet de commande de migration de Response Group déplace la configuration de Response Group pour l’intégralité du pool. Vous ne pouvez pas sélectionner des groupes spécifiques, des files d’attente ou des flux de travail à migrer. 
  
Après avoir migré les groupes Response Group, vous devez utiliser Skype pour le panneau de configuration serveur Business ou Skype pour les applets de commande Business Server Management Shell pour vérifier que tous les groupes d’agents, files d’attente et flux de travail déplacés avec succès. 
  
Lorsque vous migrez des groupes de réponses, les groupes Response Group hérités ne sont pas supprimés. Lorsque vous gérez des groupes de réponses après la migration à l’aide de deux Skype pour le panneau de configuration serveur Business ou Skype pour Business Server Management Shell, vous pouvez voir les groupes Response Group hérités et le Skype pour les groupes de réponse Business Server 2019. Vous devez appliquer les mises à jour uniquement à la Skype pour les groupes de réponse Business Server 2019. Les groupes Response Group hérités sont conservées uniquement à des fins de restauration. 
  
> [!CAUTION]
> Une fois la migration est terminée et les nouveaux groupes de réponse ont été créés, le Skype pour le panneau de configuration serveur Business et le Skype pour Business Server Management Shell affichera hérité et Skype pour les versions Business Server 2019 de chaque réponse. groupe. N’utilisez pas Skype pour le panneau de configuration serveur Business ou Skype pour Business Server Management Shell pour supprimer les groupes Response Group hérités. Si vous supprimez un, le groupe Response Group correspondante qui a été créé lors de la migration cessera de fonctionner. Les groupes Response Group hérités seront supprimés lorsque vous mettez hors service le pool hérité. 
  
> [!IMPORTANT]
> Nous vous recommandons de ne pas supprimer toutes les données de votre déploiement précédent jusqu'à ce que vous mettez hors service le pool. En outre, il est vivement recommandé que vous exportez des groupes de réponses immédiatement après la migration. Si un groupe Response Group hérités doit obtenir supprimé, vous pouvez ensuite restaurer vos groupes Response Group à partir de la sauvegarde pour obtenir Skype pour les groupes de réponses Business Server 2019 exécute à nouveau. 
  
Skype pour Business Server 2019 présente une nouvelle fonctionnalité de Response Group appelée le **Type de flux de travail**. **Type de flux de travail** peuvent être **gérés** ou **non gérés**. Tous les groupes de réponse sont migrés avec le **Type de flux de travail** , la valeur **non géré** et avec une liste vide de gestionnaire. 
  
Lorsque vous exécutez l’applet de commande **Move-CsRgsConfiguration** , les groupes d’agents, files d’attente, flux de travail et les fichiers audio restent dans le pool hérité à des fins de restauration. Si vous n’avez pas besoin de restaurer le pool hérité, toutefois, vous devez exécuter l’applet de commande **Move-CsApplicationEndpoint** pour déplacer les objets contact retour vers le pool hérité. 
  
La procédure suivante pour migrer des configurations Response Group suppose que vous disposez d’une relation entre vos pools hérités et le Skype pour les pools d’entreprise Server 2019. Si vous prévoyez de consolider ou fractionner des pools au cours de votre déploiement et de migration, vous devez planifier le pool hérité mappe sur quels Skype pour Business Server 2019 pool.
  
## <a name="to-migrate-response-group-configurations"></a>Pour migrer les configurations de Response Group

1. Ouvrez une session l’ordinateur avec un compte qui est membre du groupe RTCUniversalServerAdmins ou disposant d’autorisations et droits d’administrateur équivalents.
    
2. Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Microsoft Skype pour Business Server 2019**, puis cliquez sur **Skype pour Business Server Management Shell**.
    
3. Exécutez :
    
   ```
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    Par exemple :
    
   ```
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. Après avoir migré les groupes de réponses et les agents à la Skype pour le pool d’entreprise Server 2019, l’URL que les agents utilisent pour se connecter et se déconnecter est un Skype pour Business 2019 URL et est disponible dans le menu **Outils** . Rappeler les agents à mettre à jour toutes les références, telles que des signets, vers la nouvelle URL. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a>Pour vérifier la migration de Response Group à l’aide de Skype pour Business Server Control Panel

1. Ouvrez une session l’ordinateur avec un compte qui est membre du groupe RTCUniversalReadOnlyAdmins ou qui est au moins un membre du rôle CsViewOnlyAdministrator.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer Skype pour le panneau de configuration serveur Business, voir [Open Skype pour les outils d’administration Business Server 2019](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx). 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. Dans le volet de navigation de gauche, cliquez sur **Groupes Response Group**.
    
4. Sous l’onglet **flux de travail** , vérifiez que tous les flux de travail de votre environnement hérité est inclus dans la liste. 
    
5. Cliquez sur l’onglet **file d’attente** et vérifiez que toutes les files d’attente dans votre environnement hérité sont inclus dans la liste. 
    
6. Cliquez sur l’onglet **groupe** et vérifiez que tous les groupes d’agents de votre environnement hérité sont inclus dans la liste. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a>Pour vérifier la migration de Response Group à l’aide de Skype pour Business Server Management Shell

1. Ouvrez une session l’ordinateur avec un compte qui est membre du groupe RTCUniversalReadOnlyAdmins ou qui est au moins un membre du rôle CsViewOnlyAdministrator.
    
2. Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Microsoft Skype pour Business Server 2019**, puis cliquez sur **Skype pour Business Server Management Shell**.
    
    Pour plus d’informations sur les applets de commande suivantes, exécutez :
    
   ```
   Get-Help <cmdlet name> -Detailed
   ```

3. Exécutez :
    
   ```
   Get-CsRgsAgentGroup
   ```

4. Vérifiez que tous les groupes d’agents de votre environnement hérité sont inclus dans la liste.
    
5. Exécutez :
    
   ```
   Get-CsRgsQueue
   ```

6. Vérifiez que toutes les files d’attente dans votre environnement hérité sont inclus dans la liste.
    
7. Exécutez :
    
   ```
   Get-CsRgsWorkflow
   ```

8. Vérifiez que tous les flux de travail de votre environnement hérité est inclus dans la liste.
    

