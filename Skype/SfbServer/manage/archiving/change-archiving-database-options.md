---
title: Modifier les options de base de données d’archivage dans Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: 'Résumé : Découvrez comment modifier les options de base de données d’archivage Skype Entreprise Server.'
ms.openlocfilehash: 7a6d0c5168eded42a45996cb8154c4dd6f757a4c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399758"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a>Modifier les options de base de données d’archivage dans Skype Entreprise Server

**Résumé :** Découvrez comment modifier les options de base de données d’archivage Skype Entreprise Server.
  
Si vous déployez l’archivage à l’aide SQL Server stockage d’archivage pour l’un de vos utilisateurs, vous pouvez apporter les modifications suivantes au stockage de base de données :
  
- Utilisez une base de données SQL Server d’archivage différente. Cela inclut la base de données d’archivage principale et toute base de données que vous utilisez pour SQL Server miroir.
    
- Basculez vers l’intégration Exchange Microsoft pour stocker les données d’archivage et les fichiers sur Exchange serveurs. Si tous vos utilisateurs sont stockés sur vos serveurs Exchange et que vous souhaitez utiliser le stockage Microsoft Exchange pour tous les utilisateurs de votre déploiement, vous devez supprimer les bases de données du magasin SQL Server de votre topologie. 
    
Pour apporter l’une de ces modifications, vous devez exécuter le Générateur de topologies, effectuer les modifications, puis publier à nouveau la topologie. Ne spécifiez  pas les informations de mise en SQL Server du magasin  d’archivage ou Activer SQL Server store, sauf si vous avez des utilisateurs Skype Entreprise qui ne sont pas Exchange serveurs.
  
## <a name="change-archiving-database-options"></a>Modifier les options de la base de données d’archivage

1. Sur un ordinateur qui exécute Skype Entreprise Server ou sur lequel les outils d’administration Skype Entreprise Server sont installés, connectez-vous à l’aide d’un compte membre du groupe Utilisateurs local (ou d’un compte avec des droits d’utilisateur équivalents).
    
    > [!NOTE]
    > Vous pouvez définir une topologie à l’aide d’un compte membre du groupe Utilisateurs local, mais pour publier une topologie, qui est requise pour ajouter un composant à la topologie, vous devez utiliser un compte membre du groupe **Administrateurs** du domaine et du groupe **RTCUniversalServerAdmins**, qui dispose d’autorisations de contrôle total (c’est-à-dire,  lire, écrire et modifier) sur le partage de fichiers que vous utilisez pour le magasin de fichiers Skype Entreprise Server (c’est-à-dire, pour que le Générateur de topologie puisse configurer les listes de contrôle d’accès discrétionnaire (DAC) requises, ou un compte avec des droits équivalents.
  
2. Démarrez le Générateur de topologie.
    
3. Dans l’arborescence de la console, accédez au pool de serveurs frontaux dans lequel vous avez déployé l’archivage, puis cliquez sur le nom du pool de serveurs frontaux dans lequel vous voulez modifier les options de base de données.
    
4. Dans le menu **Action**, cliquez sur **Modifier les propriétés**. 
    
5. Dans la boîte de dialogue **Modifier les propriétés**, cliquez sur **Général**.
    
6. Faites défiler la liste jusqu’à **Archivage**.
    
7. Dans **Archivage**, procédez comme suit :
    
   - Pour choisir un autre magasin SQL Server existant, sous **Magasin SQL Server d’archivage**, dans la zone de liste déroulante, procédez comme suit :
    
   - Pour utiliser un magasin SQL Server existant, dans la zone de liste déroulante, cliquez sur le nom du magasin SQL Server que vous voulez utiliser.
    
   - Pour spécifier un nouveau magasin SQL Server, cliquez sur **Nouveau**, puis dans la boîte de dialogue **Définir un nouveau magasin SQL Server**, procédez comme suit :
    
     - Pour utiliser un magasin SQL Server existant, dans la zone de liste déroulante, cliquez sur le nom du magasin SQL Server que vous voulez utiliser.
    
     - Pour spécifier une nouvelle SQL Server store, cliquez sur **Nouveau, puis** dans la boîte de dialogue Définir **SQL Server Store**, faites les choses suivantes :
    
       - Dans **SQL Server FQDN**, spécifiez le nom de SQL Server serveur sur lequel vous souhaitez créer le magasin.
    
       - Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou, pour définir une instance différente, cliquez sur **Instance nommée** et spécifiez l’instance à utiliser.
    
       - Si l’instance de SQL Server spécifiée se trouve dans une relation de mise en miroir, sélectionnez la case à cocher Cette **instance SQL se** trouve dans la relation de mise en miroir, puis, dans le numéro de **port** Miroir, spécifiez le numéro de port.
    
   - Pour ajouter le magasin SQL Server ou choisir un autre magasin SQL Server existant pour la mise en miroir, sélectionnez **Activer la mise en miroir du magasin SQL Server**, puis procédez comme suit :
    
     - Pour utiliser un magasin de SQL Server existant pour la mise en miroir, dans la zone  de liste de listes de listes SQL Server miroir du magasin d’archivage, cliquez sur le nom du magasin SQL Server que vous souhaitez utiliser pour la mise en miroir.
    
     - Pour spécifier un nouveau magasin SQL Server pour la mise en miroir, cliquez sur **Nouveau, puis** dans la  boîte de dialogue Définir un nouveau magasin SQL Server, faites l’une des choses suivantes :
    
       a. Dans **SQL Server FQDN**, spécifiez le FQDN du SQL Server sur lequel vous souhaitez créer le nouveau magasin SQL Server de données.
    
       b. Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou sur **Instance nommée** pour définir une instance différente, puis spécifiez l’instance à utiliser.
    
       c. Si l’instance de SQL Server spécifiée se trouve dans une relation de mise en miroir, sélectionnez la case à cocher Cette **instance SQL se** trouve dans la relation de mise en miroir, puis, dans le numéro de **port** Miroir, spécifiez le numéro de port.
    
   - Si vous activez la mise en miroir SQL Server et que vous souhaitez ajouter ou modifier un témoin de mise en miroir SQL Server (une troisième instance de SQL Server distincte qui peut détecter l’état d’état du serveur SQL Server principal et des instances miroir), sélectionnez le témoin de mise en miroir Utiliser SQL Server pour activer le changement automatique **.**  case à cocher, puis faites l’une des choses suivantes :
    
      a. Dans **SQL Server FQDN**, spécifiez le nom de SQL Server serveur sur lequel vous souhaitez créer le témoin de mise en miroir.
    
      b. Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou sur **Instance nommée** pour définir une instance différente, puis spécifiez l’instance à utiliser comme témoin de mise en miroir.
    
      c. Si l’instance de SQL Server spécifiée se trouve dans une relation de mise en miroir, sélectionnez la case à cocher Cette **instance SQL se** trouve dans la relation de mise en miroir, puis, dans le numéro de **port** Miroir, spécifiez le numéro de port.
    
   - Pour basculer vers l’intégration Microsoft Exchange afin de stocker les données d’archivage et les fichiers sur des serveurs Exchange (si tous les utilisateurs de votre déploiement sont stockés sur vos serveurs Exchange), supprimez toutes les informations relatives aux bases de données d’archivage.
    
     > [!IMPORTANT]
     > Si vous avez des utilisateurs Skype Entreprise qui ne sont pas dossés sur des serveurs Exchange, ne supprimez pas les SQL Server stockent des informations. 
  
8. Pour enregistrer la configuration, cliquez sur **OK**.
    
    > [!IMPORTANT]
    > Les modifications apportées dans le Générateur de topologie ne prennent effet qu’une fois que vous avez publié la nouvelle topologie. Pour plus d’informations, voir [Ajouter des bases de données d’archivage à un déploiement existant dans Skype Entreprise Server](../../deploy/deploy-archiving/add-archiving-databases.md). 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a>Modifier l’emplacement de la base de données d’archivage à l’aide Windows PowerShell

Dans la plupart des cas, vous n’aurez pas besoin de modifier l’emplacement de la base de données d’archivage, qui est spécifié lors de l’installation du serveur d’archivage. Toutefois, en cas de défaillance matérielle ou d’un autre problème, vous pouvez pointer le serveur d’archivage vers une nouvelle base de données à l’aide de l **';**
  
L’exemple suivant modifie l’emplacement de la base de données d’archivage pour le serveur d’archivage ArchivingServer:atl-cs-001.contoso.com Archiving Server. Dans cet exemple, la nouvelle base de données se trouve à l’emplacement ArchivingDatabase:atl-sql-001.contoso.com :
  
```PowerShell
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


