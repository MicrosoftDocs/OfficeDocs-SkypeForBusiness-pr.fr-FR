---
title: Migration de groupes de réponses
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Une fois vos utilisateurs déplacés vers Skype Entreprise Server 2019, vous pouvez migrer vos groupes Response Groups. La migration de groupes Response Group inclut la copie des groupes d’agents, des files d’attente, des flux de travail, des fichiers audio et le déplacement d’objets contact Response Group du déploiement hérité vers le pool Skype Entreprise Server 2019. Après avoir migré vos groupes Response Group hérités, les appels aux groupes Response Group sont gérés par l’application Response Group dans le pool Skype Entreprise Server 2019. Les appels destinés aux groupes Response Group ne sont plus gérés par le pool hérité.
ms.openlocfilehash: 83edbfd97fac08aded66ce042adecda9fee7b539588e717323eeaeda36003041
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303558"
---
# <a name="migrate-response-groups"></a>Migration de groupes de réponses

Une fois vos utilisateurs déplacés vers Skype Entreprise Server 2019, vous pouvez migrer vos groupes Response Groups. La migration de groupes Response Group inclut la copie des groupes d’agents, des files d’attente, des flux de travail, des fichiers audio et le déplacement d’objets contact Response Group du déploiement hérité vers le pool Skype Entreprise Server 2019. Après avoir migré vos groupes Response Group hérités, les appels aux groupes Response Group sont gérés par l’application Response Group dans le pool Skype Entreprise Server 2019. Les appels destinés aux groupes Response Group ne sont plus gérés par le pool hérité.
  
> [!NOTE]
> Bien que vous pouvez migrer des groupes Response Groups avant de déplacer tous les utilisateurs vers le pool Skype Entreprise Server 2019, nous vous recommandons de déplacer tous les utilisateurs en premier. En particulier, les utilisateurs qui sont des agents Response Group n’auront pas toutes les fonctionnalités des nouvelles fonctionnalités tant qu’ils n’auront pas été déplacés vers le pool Skype Entreprise Server 2019. 
  
Avant de migrer des groupes Response Group, vous devez avoir déployé un pool Skype Entreprise Server 2019 qui inclut l’application Response Group. L’application Response Group est installée et activée par défaut lorsque vous déployez Voix Entreprise. Vous pouvez vous assurer que l’application Response Group est installée en exécutant l’cmdlet **Get-CsService -ApplicationServer.** 
  
> [!NOTE]
> Vous pouvez créer des groupes Response Skype Entreprise Server 2019 dans le pool Skype Entreprise Server 2019 avant de migrer vos groupes Response Groups hérités. 
  
Pour migrer des groupes Response Groups d’un pool hérité vers Skype Entreprise Server 2019, vous exécutez l';cmdlet **Move-CsRgsConfiguration.** 
  
> [!IMPORTANT]
> L’cmdlet de migration Response Group déplace la configuration Response Group pour l’ensemble du pool. Vous ne pouvez pas sélectionner de groupes, files d’attente ou flux de travail spécifiques à migrer. 
  
Après avoir migré les groupes Response Groups, vous devez utiliser le Panneau de Skype Entreprise Server ou les cmdlets Skype Entreprise Server Management Shell pour vérifier que tous les groupes d’agents, files d’attente et flux de travail ont bien été déplacés. 
  
Lorsque vous migrez des groupes Response Groups, les groupes Response Groups hérités ne sont pas supprimés. Lorsque vous gérez des groupes Response Groups après la migration à l’aide du Panneau de Skype Entreprise Server ou de Skype Entreprise Server Management Shell, vous pouvez voir les groupes Response Groups hérités et les groupes Response Groups Skype Entreprise Server 2019. Vous devez appliquer les mises à jour uniquement aux groupes Response Skype Entreprise Server 2019. Les groupes Response Groups hérités sont conservés uniquement à des fins de récupération. 
  
> [!CAUTION]
> Une fois la migration terminée et les nouveaux groupes Response Group créés, le Panneau de contrôle Skype Entreprise Server et l’environnement de ligne de commande Skype Entreprise Server Management Shell affichent les versions héritées et Skype Entreprise Server 2019 de chaque groupe Response Group. N’utilisez pas Skype Entreprise Server De control Panel ou Skype Entreprise Server Management Shell pour supprimer les groupes Response Groups hérités. Si vous en supprimez un, le groupe Response Group correspondant qui a été créé lors de la migration cessera de fonctionner. Les groupes Response Groups hérités seront supprimés lorsque vous désaffectez le pool hérité. 
  
> [!IMPORTANT]
> Nous vous recommandons de ne pas supprimer les données de votre déploiement précédent tant que vous n’avez pas désaffecté le pool. En outre, nous vous recommandons fortement d’exporter les groupes Response Group immédiatement après la migration. Si un groupe Response Group hérité doit être supprimé, vous pouvez restaurer vos groupes Response Group à partir de la sauvegarde pour que les groupes Response Group Skype Entreprise Server 2019 s’exécutent à nouveau. 
  
Skype Entreprise Server 2019 introduit une nouvelle fonctionnalité Response Group appelée Type de **flux de travail.** Le **Type de flux de travail** peut être **Géré** ou **Non géré**. Tous les groupes Response Group sont migrés avec le **Type de flux de travail** défini à **Non géré** et avec une liste de gestionnaires vide. 
  
Quand vous exécutez l’applet de commande **Move-CsRgsConfiguration**, les groupes d’agents, les files d’attente, les flux de travail et les fichiers audio restent dans le pool hérité à des fins de restauration. Cependant, si vous devez restaurer le pool hérité, vous devez exécuter l’applet de commande **Move-CsApplicationEndpoint**. Les objets contact seront ainsi replacés dans le pool hérité. 
  
La procédure suivante pour la migration des configurations Response Group suppose que vous avez une relation un-à-un entre vos pools hérités et les pools Skype Entreprise Server 2019. Si vous prévoyez de consolider ou de fractionner des pools lors de votre migration et déploiement, vous devez planifier le pool hérité map Skype Entreprise Server pool 2019.
  
## <a name="to-migrate-response-group-configurations"></a>Pour migrer des configurations Response Group

1. Ouvrez une session sur l’ordinateur en utilisant un compte membre du groupe RTCUniversalServerAdmins ou disposant de droits et d’autorisations d’administrateur équivalents.
    
2. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Microsoft Skype Entreprise Server 2019,** puis sur Skype Entreprise Server **Management Shell**.
    
3. Exécutez :
    
   ```PowerShell
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    Par exemple :
    
   ```PowerShell
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. Une fois que vous avez migré des groupes Response Groups et des agents vers le pool Skype Entreprise Server 2019, l’URL que les agents utilisent pour se connecter et se sortir est une URL Skype Entreprise Server 2019 et est disponible dans le menu **Outils.** Rappeler aux agents de mettre à jour les références, telles que les signets, à la nouvelle URL. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a>Pour vérifier la migration de Response Group à l’aide du Skype Entreprise Server de contrôle

1. Ouvrez une session sur l’ordinateur à l’aide d’un compte membre du groupe RTCUniversalReadOnlyAdmins ou qui soit au moins membre du rôle CsViewOnlyAdministrator.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer Skype Entreprise Server Panneau de Skype Entreprise Server [2019, voir Outils d’administration Open Skype Entreprise Server 2019.](/previous-versions/office/lync-server-2013/lync-server-2013-open-lync-server-administrative-tools) 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. Dans le volet de navigation gauche, cliquez sur **Services Response Group**.
    
4. Sous **l’onglet** Flux de travail, vérifiez que tous les flux de travail de votre environnement hérité sont inclus dans la liste. 
    
5. Cliquez sur **l’onglet** File d’attente et vérifiez que toutes les files d’attente de votre environnement hérité sont incluses dans la liste. 
    
6. Cliquez sur **l’onglet** Groupe et vérifiez que tous les groupes d’agents de votre environnement hérité sont inclus dans la liste. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a>Pour vérifier la migration de Response Group à l’aide Skype Entreprise Server Management Shell

1. Ouvrez une session sur l’ordinateur à l’aide d’un compte membre du groupe RTCUniversalReadOnlyAdmins ou qui soit au moins membre du rôle CsViewOnlyAdministrator.
    
2. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Microsoft Skype Entreprise Server 2019,** puis sur Skype Entreprise Server **Management Shell**.
    
    Pour plus d’informations sur les applets de commande suivantes, exécutez :
    
   ```PowerShell
   Get-Help <cmdlet name> -Detailed
   ```

3. Exécutez :
    
   ```PowerShell
   Get-CsRgsAgentGroup
   ```

4. Vérifiez que tous les groupes d’agents de votre environnement hérité sont inclus dans la liste.
    
5. Exécutez :
    
   ```PowerShell
   Get-CsRgsQueue
   ```

6. Vérifiez que toutes les files d’attente de votre environnement hérité sont incluses dans la liste.
    
7. Exécutez :
    
   ```PowerShell
   Get-CsRgsWorkflow
   ```

8. Vérifiez que tous les flux de travail de votre environnement hérité sont inclus dans la liste.
