---
title: Migrer des groupes Response Group
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Après le déplacement de vos utilisateurs vers les pools 2019 de Skype entreprise Server, vous pouvez migrer vos groupes de réponse. La migration de Response Groups inclut la copie de groupes d’agents, de files d’attente, de flux de travail, de fichiers audio et de déplacements de groupe de réponses de l’ancien déploiement vers le pool Skype entreprise Server 2019. Après avoir migré vos groupes de réponses héritées, les appels vers les groupes de réponse sont gérés par l’application Response Group dans le pool Skype entreprise Server 2019. Les appels de Response Groups ne sont plus gérés par le pool hérité.
ms.openlocfilehash: cba50526748ca15c04513013e484b0e279410c1e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298203"
---
# <a name="migrate-response-groups"></a>Migrer des groupes Response Group

Après le déplacement de vos utilisateurs vers les pools 2019 de Skype entreprise Server, vous pouvez migrer vos groupes de réponse. La migration de Response Groups inclut la copie de groupes d’agents, de files d’attente, de flux de travail, de fichiers audio et de déplacements de groupe de réponses de l’ancien déploiement vers le pool Skype entreprise Server 2019. Après avoir migré vos groupes de réponses héritées, les appels vers les groupes de réponse sont gérés par l’application Response Group dans le pool Skype entreprise Server 2019. Les appels de Response Groups ne sont plus gérés par le pool hérité.
  
> [!NOTE]
> Même si vous pouvez migrer des groupes de réponses avant de déplacer tous les utilisateurs vers le pool 2019 de Skype entreprise Server, nous vous conseillons de déplacer d’abord tous les utilisateurs. En particulier, les utilisateurs qui sont des agents de Response Group n’auront pas toutes les fonctionnalités des nouvelles fonctionnalités tant qu’ils ne seront pas déplacés vers le pool Skype entreprise Server 2019. 
  
Avant de migrer des groupes de réponse, vous devez avoir déployé un pool Skype entreprise Server 2019 incluant l’application Response Group. L’application Response Group est installée et activée par défaut lorsque vous déployez Enterprise Voice. Vous pouvez vous assurer que l’application Response Group est installée en exécutant l’applet de demande **Get-CsService-ApplicationServer** . 
  
> [!NOTE]
> Vous pouvez créer des groupes de réponse Skype entreprise Server 2019 dans le pool 2019 de Skype entreprise Server avant de migrer vos groupes de réponse hérités. 
  
Pour migrer des groupes de réponse d’un pool hérité vers Skype entreprise Server 2019, vous exécutez l’applet de **passe Move-CsRgsConfiguration** . 
  
> [!IMPORTANT]
> L’applet de passe de migration de groupe de réponse déplace la configuration de groupe de réponse pour le pool entier. Vous ne pouvez pas sélectionner des groupes, des files d’attente ou des flux de travail spécifiques à migrer. 
  
Après avoir migré les groupes de réponse, vous devez utiliser le panneau de configuration Skype entreprise Server ou les applets de commande Skype entreprise Server Management Shell pour vérifier que tous les groupes d’agents, files d’attente et flux de travail sont déplacés correctement. 
  
Lorsque vous migrez des groupes de réponse, les groupes de réponse hérités ne sont pas supprimés. Lorsque vous gérez des groupes de réponse après une migration à l’aide du panneau de configuration Skype entreprise Server ou de l’interpréteur de commandes Skype entreprise Server Management Shell, vous pouvez voir les groupes de réponse hérités et les groupes de réponse Skype entreprise Server 2019. Vous devez appliquer les mises à jour uniquement aux groupes de réponse Skype entreprise Server 2019. Les groupes de réponse hérités sont conservés uniquement à des fins de restauration. 
  
> [!CAUTION]
> Une fois la migration effectuée et les nouveaux groupes de réponse créés, le panneau de configuration Skype entreprise Server et Skype entreprise Server Management Shell affichent les versions d’anciens et de Skype entreprise Server 2019 de chaque réponse. Groupe. N’utilisez pas le panneau de configuration Skype entreprise Server ou Skype entreprise Server Management Shell pour supprimer les groupes de réponse hérités. Si vous supprimez un, le groupe de réponse correspondant qui a été créé lors de la migration ne fonctionnera plus. Les groupes de réponse hérités seront supprimés lorsque vous désaffecterez le pool hérité. 
  
> [!IMPORTANT]
> Nous vous recommandons de ne pas supprimer les données de votre déploiement antérieur tant que vous n’avez pas désactivé le pool. Par ailleurs, nous vous conseillons vivement d’exporter des groupes de réponse immédiatement après la migration. Si un groupe de réponse héritée doit être supprimé, vous pouvez restaurer vos groupes de réponse à partir de la sauvegarde pour obtenir de nouveau les groupes de réponse Skype entreprise Server 2019 en cours d’exécution. 
  
Skype entreprise Server 2019 introduit une nouvelle fonctionnalité de groupe de réponse appelée **type de flux de travail**. Le **type de flux de travail** peut être **géré** ou **non**géré. Tous les groupes de réponses sont migrés avec le **type de flux de travail** défini sur **non géré** et avec une liste de gestionnaires vide. 
  
Lorsque vous exécutez l’applet de cmdlet **Move-CsRgsConfiguration** , les groupes d’agents, les files d’attente, les flux de travail et les fichiers audio restent dans le pool hérité à des fins de restauration. Toutefois, si vous avez besoin de revenir au pool hérité, vous devez exécuter l’applet de passe **Move-CsApplicationEndpoint** pour replacer les objets de contact sur le pool hérité. 
  
La procédure suivante pour la migration de configurations de groupe de réponse suppose que vous disposez d’une relation un-à-un entre vos pools hérités et les pools 2019 de Skype entreprise Server. Si vous envisagez de consolider ou de fractionner des listes lors de la migration et du déploiement, vous devez planifier les mappages de réserve héritée vers le pool 2019 de Skype entreprise Server.
  
## <a name="to-migrate-response-group-configurations"></a>Pour migrer les configurations de Response Group

1. Ouvrez une session sur l’ordinateur avec un compte membre du groupe RTCUniversalServerAdmins ou disposant d’autorisations et de droits d’administrateur équivalents.
    
2. Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Microsoft Skype entreprise Server 2019**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
3. Exécutez :
    
   ```
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    Par exemple :
    
   ```
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. Après avoir migré des groupes de réponses et des agents vers le pool Skype entreprise Server 2019, l’URL que les agents utilisent pour se connecter et se déconnecter est une URL de Skype entreprise Server 2019 et est disponible dans le menu **Outils** . Rappelez aux agents de mettre à jour les références, comme les signets, à la nouvelle URL. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a>Pour vérifier la migration du groupe de réponse à l’aide du panneau de configuration Skype entreprise Server

1. Ouvrez une session sur l’ordinateur avec un compte membre du groupe RTCUniversalReadOnlyAdmins ou qui est membre du rôle CsViewOnlyAdministrator.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Skype entreprise Server, reportez-vous à la rubrique [ouverture des outils d’administration 2019 de Skype entreprise Server](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx). 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. Dans le volet de navigation de gauche, cliquez sur **Response Groups**.
    
4. Dans l’onglet **flux de travail** , assurez-vous que tous les flux de travail de votre environnement hérité sont inclus dans la liste. 
    
5. Cliquez sur l’onglet **file d’attente** , puis vérifiez que toutes les files d’attente de votre environnement hérité sont incluses dans la liste. 
    
6. Cliquez sur l’onglet **groupe** , puis vérifiez que tous les groupes d’agents de votre environnement hérité sont inclus dans la liste. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a>Pour vérifier la migration de groupe de réponse à l’aide de Skype entreprise Server Management Shell

1. Ouvrez une session sur l’ordinateur avec un compte membre du groupe RTCUniversalReadOnlyAdmins ou qui est membre du rôle CsViewOnlyAdministrator.
    
2. Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Microsoft Skype entreprise Server 2019**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
    Pour plus d’informations sur les applets de commande suivantes, exécutez:
    
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

6. Vérifiez que toutes les files d’attente dans votre environnement hérité sont incluses dans la liste.
    
7. Exécutez :
    
   ```
   Get-CsRgsWorkflow
   ```

8. Vérifiez que tous les flux de travail de votre environnement hérité sont inclus dans la liste.
    

