---
title: Ajouter des bases de données d’archivage à un déploiement existant dans Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: quickstart
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: 'Résumé : Lisez cette rubrique pour découvrir comment ajouter des bases de données d’archivage à Skype Entreprise Server déploiement.'
ms.openlocfilehash: 3bc4e14998e45803518436bb180906e9c79e14f4
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62401578"
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server"></a>Ajouter des bases de données d’archivage à un déploiement existant dans Skype Entreprise Server
 
**Résumé :** Lisez cette rubrique pour découvrir comment ajouter des bases de données d’archivage à Skype Entreprise Server déploiement.
  
Vous devez incorporer l’archivage dans votre topologie avant de configurer votre déploiement pour qu’il prenne en charge l’archivage. Les informations de cette rubrique expliquent comment utiliser le Générateur de topologie pour :
  
- Ajoutez une base de données d’archivage à votre topologie.
    
- Publiez la topologie mise à jour pour ajouter la base de données d’archivage à Skype Entreprise Server déploiement.
    
> [!NOTE]
> Si vous souhaitez utiliser l’intégration De Microsoft Exchange pour stocker les données d’archivage et les fichiers sur des serveurs Exchange pour tous vos utilisateurs dans votre déploiement, ne spécifiez pas de magasin d’archivage **SQL Server** ou utilisez les informations de mise en miroir du **SQL Server Store**.
  
### <a name="add-an-archiving-database-to-your-topology"></a>Ajouter une base de données d’archivage à votre topologie

1. Sur un ordinateur qui exécute Skype Entreprise Server ou sur lequel les outils d’administration Skype Entreprise Server sont installés, connectez-vous à l’aide d’un compte membre du groupe Utilisateurs local (ou d’un compte avec des droits d’utilisateur équivalents).
    
2. Démarrez le Générateur de topologie.
    
3. Dans l’arborescence de la console, accédez au pool frontal dans lequel vous souhaitez déployer l’archivage, puis cliquez sur le nom du pool frontal où vous souhaitez déployer l’archivage.
    
4. Dans le menu **Action**, cliquez sur **Modifier les propriétés**. 
    
5. Dans la boîte de dialogue **Modifier les propriétés**, cliquez sur **Général**.
    
6. Faites défiler la liste jusqu’à **Archivage**.
    
7. Activez la case à cocher **Archivage**.
    
8. Sous **Archiver SQL Server store, faites** l’une des opérations suivantes :
    
   - Pour utiliser un magasin SQL Server existant, dans la zone de liste déroulante, cliquez sur le nom du magasin SQL Server que vous voulez utiliser. Si tous vos utilisateurs sont Microsoft Exchange Server 2013 ou supérieur, vous pouvez archiver les communications Skype Entreprise de tous vos utilisateurs dans Exchange. Dans ce cas, vous n’avez pas besoin de configurer SQL Server d’archivage.
    
   - Pour spécifier une nouvelle SQL Server store, cliquez sur **Nouveau, puis** dans la boîte de dialogue Définir **SQL Server Store**, faites les choses suivantes :
    
   - Dans **SQL Server FQDN**, spécifiez le nom de SQL Server serveur sur lequel vous souhaitez créer le magasin.
    
   - Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou, pour définir une instance différente, cliquez sur **Instance nommée** et spécifiez l’instance à utiliser.
    
   - Si l’instance de SQL Server spécifiée se trouve dans une relation de mise en miroir, sélectionnez la case à cocher Cette **instance SQL se** trouve dans la relation de mise en miroir, puis, dans le numéro de **port** Miroir, spécifiez le numéro de port.
    
9. Si vous souhaitez utiliser la mise en SQL Server de la boutique d’SQL Server, sélectionnez Activer la mise en miroir du **Store**, puis faites les choses suivantes :
    
   - Pour utiliser un magasin de SQL Server existant pour la mise en miroir, dans la zone  de liste de listes de listes SQL Server miroir du magasin d’archivage, cliquez sur le nom du magasin SQL Server que vous souhaitez utiliser pour la mise en miroir.
    
   - Pour spécifier un nouveau magasin SQL Server pour la mise en miroir, cliquez sur **Nouveau, puis** dans la  boîte de dialogue Définir un nouveau magasin SQL Server, faites l’une des choses suivantes :
    
     a. Dans **SQL Server FQDN**, spécifiez le FQDN du SQL Server sur lequel vous souhaitez créer le nouveau magasin SQL Server de données.
    
     b. Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou sur **Instance nommée** pour définir une instance différente, puis spécifiez l’instance à utiliser.
    
     c. Si l’instance de SQL Server spécifiée se trouve dans une relation de mise en miroir, sélectionnez la case à cocher Cette **instance SQL se** trouve dans la relation de mise en miroir, puis, dans le numéro de **port** Miroir, spécifiez le numéro de port.
    
   - Si vous activez la mise en miroir SQL Server et que vous souhaitez inclure un témoin de mise en miroir SQL Server (une troisième instance de SQL Server distincte qui peut détecter l’état de l’SQL Server principale et des instances miroir), sélectionnez le témoin de mise en miroir Utiliser **SQL Server** pour activer leover automatique  case à cocher, puis faites l’une des choses suivantes :
    
     a. Dans **SQL Server FQDN**, spécifiez le nom de SQL Server serveur sur lequel vous souhaitez créer le témoin de mise en miroir.
    
     b. Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou sur **Instance nommée** pour définir une instance différente, puis spécifiez l’instance à utiliser comme témoin de mise en miroir.
    
     c. Si l’instance de SQL Server spécifiée se trouve dans une relation de mise en miroir, sélectionnez la case à cocher Cette **instance SQL se** trouve dans la relation de mise en miroir, puis, dans le numéro de **port** Miroir, spécifiez le numéro de port.
    
10. Pour enregistrer la configuration, cliquez sur **OK**.
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a>Publier la topologie mise à jour pour ajouter une base de données d’archivage à votre déploiement

1. Sur un ordinateur qui exécute Skype Entreprise Server ou sur lequel les outils d’administration Skype Entreprise Server sont installés, connectez-vous à l’aide d’un compte membre du groupe Utilisateurs local (ou d’un compte avec des droits d’utilisateur équivalents).
    
    > [!NOTE]
    > Vous pouvez définir une topologie à l’aide d’un compte membre du groupe Utilisateurs local, mais pour publier une topologie requise pour ajouter un serveur à la topologie, vous devez utiliser un compte membre du groupe **Administrateurs** du domaine et du groupe **RTCUniversalServerAdmins**, et qui dispose d’autorisations de contrôle total (lecture,  écrire et modifier) sur le partage de fichiers que vous utilisez pour le magasin de fichiers Skype Entreprise Server (afin que le Générateur de topologie puisse configurer la liste de contrôle d’accès discrétionnaire (DAC) requise ou un compte avec des droits équivalents.
  
2. Ouvrez la topologie que vous avez créée dans la section précédente à l’aide du Générateur de topologies.
    
3. Dans l’arborescence de la console, cliquez **Skype Entreprise Server**, puis cliquez sur **Publier la topologie**.
    
4. Dans la page **Publier la topologie**, cliquez sur **Suivant**.
    
5. Dans la page **Créer des bases de données**, vérifiez que la base de données est sélectionnée, puis cliquez sur **Suivant**. 
    
    > [!NOTE]
    > Si vous ne disposez pas des autorisations appropriées pour créer des bases de données, vous pouvez annuler la sélection de la base de données et laisser une autre personne dotée des autorisations nécessaires la créer. > seules les bases de données sur des serveurs SQL dédiés peuvent être installées à l’aide du Générateur de topologie. Les bases de données situées sur des serveurs SQL Server colocalisés avec d’autres composants serveur doivent être installées via une installation locale sur l’ordinateur concerné. 
  
6. Sur la page **Assistant Publication terminé**, assurez-vous que la topologie a été publiée comme il se doit, puis cliquez sur **Terminer**.
    
    > [!IMPORTANT]
    > Une fois la topologie publiée, vous devez configurer les options et les stratégies relatives à l’archivage pour permettre l’archivage du contenu. Pour plus d’informations, voir [Configure archiving options for Skype Entreprise Server](configure-archiving-options.md) and [Configure archiving policies for Skype Entreprise Server](configure-archiving-policies.md). 
  

