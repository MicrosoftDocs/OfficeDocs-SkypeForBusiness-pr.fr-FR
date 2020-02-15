---
title: Effectuer la migration de groupes Response Group
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Une fois les utilisateurs déplacés vers les pools Skype entreprise Server 2019, vous pouvez migrer vos groupes Response Group. La migration de groupes Response Group consiste à copier des groupes d’agents, des files d’attente, des flux de travail, des fichiers audio et des objets de contact de groupe Response Group à partir du déploiement hérité vers le pool Skype entreprise Server 2019. Une fois vos groupes de réponse hérités migrés, les appels vers les groupes Response Group sont gérés par l’application Response Group dans le pool Skype entreprise Server 2019. Les appels destinés aux groupes Response Group ne sont plus gérés par le pool hérité.
ms.openlocfilehash: 2d439462fa103cc16fd7ae70b79364be7d79803a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42016105"
---
# <a name="migrate-response-groups"></a>Effectuer la migration de groupes Response Group

Une fois les utilisateurs déplacés vers les pools Skype entreprise Server 2019, vous pouvez migrer vos groupes Response Group. La migration de groupes Response Group consiste à copier des groupes d’agents, des files d’attente, des flux de travail, des fichiers audio et des objets de contact de groupe Response Group à partir du déploiement hérité vers le pool Skype entreprise Server 2019. Une fois vos groupes de réponse hérités migrés, les appels vers les groupes Response Group sont gérés par l’application Response Group dans le pool Skype entreprise Server 2019. Les appels destinés aux groupes Response Group ne sont plus gérés par le pool hérité.
  
> [!NOTE]
> Bien que vous puissiez migrer des groupes Response Group avant de déplacer tous les utilisateurs vers le pool Skype entreprise Server 2019, nous vous recommandons de déplacer tous les utilisateurs en premier. En particulier, les utilisateurs qui sont des agents Response Group ne disposent pas de toutes les fonctionnalités des nouvelles fonctionnalités tant qu’ils ne sont pas déplacés vers le pool Skype entreprise Server 2019. 
  
Avant de migrer les groupes Response Group, vous devez avoir déployé un pool Skype entreprise Server 2019 qui inclut l’application Response Group. L’application Response Group est installée et activée par défaut lorsque vous déployez voix entreprise. Vous pouvez vous assurer que l’application Response Group est installée en exécutant la cmdlet **Get-CsService-ApplicationServer** . 
  
> [!NOTE]
> Vous pouvez créer des groupes de réponses Skype entreprise Server 2019 dans le pool de Skype entreprise Server 2019 avant de migrer vos groupes de réponse hérités. 
  
Pour migrer des groupes Response Group d’un pool hérité vers Skype entreprise Server 2019, exécutez l’applet de commande **Move-applet csrgsconfiguration** . 
  
> [!IMPORTANT]
> La cmdlet Response Group migration déplace la configuration Response Group pour l’ensemble du pool. Vous ne pouvez pas sélectionner de groupes, files d’attente ou flux de travail spécifiques à migrer. 
  
Après avoir migré les groupes Response Group, vous devez utiliser le panneau de configuration de Skype entreprise Server ou les applets de commande Skype entreprise Server Management Shell pour vérifier que tous les groupes d’agents, files d’attente et flux de travail ont été déplacés avec succès. 
  
Lorsque vous migrez des groupes Response Group, les groupes Response Group hérités ne sont pas supprimés. Lorsque vous gérez des groupes Response Group après une migration à l’aide du panneau de configuration de Skype entreprise ou de Skype entreprise Server Management Shell, vous pouvez voir les groupes Response Group hérités et Skype entreprise Server 2019 Response groups. Vous devez appliquer les mises à jour uniquement aux groupes Response Group de Skype entreprise Server 2019. Les groupes Response Group hérités ne sont conservés qu’à des fins de restauration. 
  
> [!CAUTION]
> Une fois que la migration est terminée et que les nouveaux groupes Response Group ont été créés, le panneau de configuration Skype entreprise Server et Skype entreprise Server Management Shell afficheront les versions héritées et Skype entreprise Server 2019 de chaque réponse. Communauté. N’utilisez pas le panneau de configuration Skype entreprise Server ou Skype entreprise Server Management Shell pour supprimer les groupes Response Group hérités. Si vous supprimez un, le groupe Response Group correspondant qui a été créé pendant la migration cessera de fonctionner. Les groupes Response Group hérités sont supprimés lorsque vous désactivez le pool hérité. 
  
> [!IMPORTANT]
> Nous vous recommandons de ne pas supprimer les données de votre déploiement précédent tant que vous n’avez pas désaffecté le pool. En outre, nous vous recommandons fortement d’exporter les groupes Response Group immédiatement après la migration. Si un groupe Response Group hérité doit être supprimé, vous pouvez restaurer vos groupes Response Group à partir de la sauvegarde pour obtenir les groupes de réponse Skype entreprise Server 2019 en cours d’exécution à nouveau. 
  
Skype entreprise Server 2019 introduit une nouvelle fonctionnalité Response Group appelée **type de flux de travail**. Le **Type de flux de travail** peut être **Géré** ou **Non géré**. Tous les groupes Response Group sont migrés avec le **Type de flux de travail** défini à **Non géré** et avec une liste de gestionnaires vide. 
  
Lorsque vous exécutez l’applet de commande **Move-applet csrgsconfiguration** , les groupes d’agents, les files d’attente, les flux de travail et les fichiers audio restent dans le pool hérité à des fins de restauration. Toutefois, si vous devez restaurer le pool hérité, vous devez exécuter la cmdlet **Move-CsApplicationEndpoint** pour déplacer les objets contact vers le pool hérité. 
  
La procédure suivante pour migrer des configurations de groupe Response Group suppose que vous avez une relation un-à-un entre vos pools hérités et les pools de Skype entreprise Server 2019. Si vous envisagez de consolider ou de fractionner les pools lors de la migration et du déploiement, vous devez planifier le pool hérité mappé vers le pool Skype entreprise Server 2019.
  
## <a name="to-migrate-response-group-configurations"></a>Pour migrer des configurations de groupe Response Group

1. Ouvrez une session sur l’ordinateur en utilisant un compte membre du groupe RTCUniversalServerAdmins ou disposant de droits et d’autorisations d’administrateur équivalents.
    
2. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Skype entreprise Server 2019**, puis sur **Skype entreprise Server Management Shell**.
    
3. Générer
    
   ```PowerShell
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    Par exemple :
    
   ```PowerShell
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. Une fois que vous avez migré les groupes Response Group et les agents vers le pool Skype entreprise Server 2019, l’URL que les agents utilisent pour se connecter et se déconnecter est une URL de Skype entreprise Server 2019 et est disponible dans le menu **Outils** . Rappelez aux agents de mettre à jour les références, telles que les signets, vers la nouvelle URL. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a>Pour vérifier la migration de groupes Response Group à l’aide du panneau de configuration Skype entreprise Server

1. Ouvrez une session sur l’ordinateur à l’aide d’un compte membre du groupe RTCUniversalReadOnlyAdmins ou qui soit au moins membre du rôle CsViewOnlyAdministrator.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Skype entreprise Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Skype entreprise Server, voir [Open Skype for Business server 2019 administrative Tools](https://technet.microsoft.com/library/gg195741(v=ocs.15).aspx). 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. Dans le volet de navigation gauche, cliquez sur **Services Response Group**.
    
4. Sous l’onglet **flux de travail** , vérifiez que tous les flux de travail de votre environnement hérité sont inclus dans la liste. 
    
5. Cliquez sur l’onglet **file d’attente** , puis vérifiez que toutes les files d’attente de votre environnement hérité sont incluses dans la liste. 
    
6. Cliquez sur l’onglet **groupe** , puis vérifiez que tous les groupes d’agents de votre environnement hérité sont inclus dans la liste. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a>Pour vérifier la migration de groupes Response Group à l’aide de Skype entreprise Server Management Shell

1. Ouvrez une session sur l’ordinateur à l’aide d’un compte membre du groupe RTCUniversalReadOnlyAdmins ou qui soit au moins membre du rôle CsViewOnlyAdministrator.
    
2. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Skype entreprise Server 2019**, puis sur **Skype entreprise Server Management Shell**.
    
    Pour plus d’informations sur les applets de commande suivantes, exécutez :
    
   ```PowerShell
   Get-Help <cmdlet name> -Detailed
   ```

3. Générer
    
   ```PowerShell
   Get-CsRgsAgentGroup
   ```

4. Vérifiez que tous les groupes d’agents de votre environnement hérité sont inclus dans la liste.
    
5. Générer
    
   ```PowerShell
   Get-CsRgsQueue
   ```

6. Vérifiez que toutes les files d’attente de votre environnement hérité sont incluses dans la liste.
    
7. Générer
    
   ```PowerShell
   Get-CsRgsWorkflow
   ```

8. Vérifiez que tous les flux de travail de votre environnement hérité sont inclus dans la liste.
    

